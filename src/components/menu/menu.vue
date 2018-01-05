<template>
    <ul :class="classes" :style="styles">
        <slot></slot>
        <li :class="toggleClasses" @click="miniToggle" :style="toggleStyles">
            <img class="left" :src="imgSrc.left">
            <img class="right" :src="imgSrc.right">
            <img class="leftBlue" :src="imgSrc.leftBlue">
            <img class="rightBlue" :src="imgSrc.rightBlue">
        </li>
    </ul>
</template>
<script>
    import { oneOf, findComponentsDownward, findBrothersComponents } from '../../utils/assist';
    import Emitter from '../../mixins/emitter';

    const prefixCls = 'bsc-menu';

    export default {
        name: 'Menu',
        mixins: [ Emitter ],
        props: {
            mode: {
                validator (value) {
                    return oneOf(value, ['horizontal', 'vertical']);
                },
                default: 'vertical'
            },
            theme: {
                validator (value) {
                    return oneOf(value, ['light', 'dark', 'primary']);
                },
                default: 'light'
            },
            activeName: {
                type: [String, Number]
            },
            openNames: {
                type: Array,
                default () {
                    return [];
                }
            },
            accordion: {
                type: Boolean,
                default: false
            },
            width: {
                type: String,
                default: '240px'
            },
            imgSrc: {},
            toggleTop: {
                type: String,
                default: '50%'
            }
        },
        data () {
            return {
                currentActiveName: this.activeName,
                isMini: false
            };
        },
        computed: {
            classes () {
                let theme = this.theme;
                if (this.mode === 'vertical' && this.theme === 'primary') theme = 'light';

                return [
                    `${prefixCls}`,
                    `${prefixCls}-${theme}`,
                    {
                        [`${prefixCls}-${this.mode}`]: this.mode,
                        [`${prefixCls}-mini`]: this.isMini
                    }
                ];
            },
            styles () {
                let style = {};

                if (this.mode === 'vertical' && !this.isMini) style.width = this.width;
                if (this.isMini) style.width = '60px';

                return style;
            },
            toggleClasses () {
                return `${prefixCls}-toggle`;
            },
            toggleStyles () {
                return { top: `${this.toggleTop}` };
            }
        },
        methods: {
            updateActiveName () {
                if (this.currentActiveName === undefined) {
                    this.currentActiveName = -1;
                }
                this.broadcast('Submenu', 'on-update-active-name', false);
                this.broadcast('MenuItem', 'on-update-active-name', this.currentActiveName);
            },
            updateOpenKeys (name) {
                const index = this.openNames.indexOf(name);
                if (index > -1) {
                    this.openNames.splice(index, 1);
                } else {
                    this.openNames.push(name);
                    if (this.accordion) {
                        let currentSubmenu = {};
                        findComponentsDownward(this, 'Submenu').forEach(item => {
                            if (item.name === name) currentSubmenu = item;
                        });
                        findBrothersComponents(currentSubmenu, 'Submenu').forEach(item => {
                            let index = this.openNames.indexOf(item.name);
                            this.openNames.splice(index, index >= 0 ? 1 : 0);
                        });
                        this.openNames.push(name);
                    }
                }
            },
            updateOpened () {
                const items = findComponentsDownward(this, 'Submenu');

                if (items.length) {
                    items.forEach(item => {
                        if (this.openNames.indexOf(item.name) > -1) item.opened = true;
                    });
                }
            },
            miniToggle () {
                this.isMini = !this.isMini;
                this.$emit('on-mini-change', this.isMini);
            }
        },
        mounted () {
            this.updateActiveName();
            this.updateOpened();
            this.$on('on-menu-item-select', (name) => {
                this.currentActiveName = name;
                this.$emit('on-select', name);
            });
        },
        watch: {
            openNames () {
                this.$emit('on-open-change', this.openNames);
            },
            activeName (val) {
                this.currentActiveName = val;
            },
            currentActiveName () {
                this.updateActiveName();
            }
        }
    };
</script>
