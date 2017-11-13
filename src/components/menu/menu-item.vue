<template>
    <li :class="classes" @click.stop="handleClick" :style="itemStyle"><slot></slot></li>
</template>
<script>
    import Emitter from '../../mixins/emitter';
    import { findComponentUpward } from '../../utils/assist';
    const prefixCls = 'bsc-menu';
    import mixin from './mixin';

    export default {
        name: 'MenuItem',
        mixins: [ Emitter, mixin ],
        props: {
            name: {
                type: [String, Number],
                required: true
            },
            disabled: {
                type: Boolean,
                default: false
            }
        },
        data () {
            return {
                active: false,
                parent: findComponentUpward(this, 'Menu')
            };
        },
        computed: {
            classes () {
                return [
                    `${prefixCls}-item`,
                    {
                        [`${prefixCls}-item-active`]: this.active,
                        [`${prefixCls}-item-selected`]: this.active,
                        [`${prefixCls}-item-disabled`]: this.disabled
                    }
                ];
            },
            itemStyle () {
                return this.hasParentSubmenu && this.mode !== 'horizontal' ? {
                    paddingLeft: 43 + (this.parentSubmenuNum - 1) * 24 + 'px'
                } : {};
            },
            accordion () {
                return this.parent.accordion;
            }
        },
        methods: {
            handleClick () {
                if (this.disabled) return;

                let parent = findComponentUpward(this, 'Submenu');

                if (parent) {
                    this.dispatch('Submenu', 'on-menu-item-select', this.name);
                } else {
                    this.dispatch('Menu', 'on-menu-item-select', this.name);
                }
                
                if (this.accordion && this.$parent.$options.name === 'Menu') {
                    this.parent.$children.forEach(item => {
                        if (item.$options.name === 'Submenu') item.opened = false;
                    });
                }
            }
        },
        mounted () {
            this.$on('on-update-active-name', (name) => {
                if (this.name === name) {
                    this.active = true;
                    this.dispatch('Submenu', 'on-update-active-name', name);
                } else {
                    this.active = false;
                }
            });
        }
    };
</script>
