<template>
    <div :style="circleSize" :class="wrapClasses" >
        <svg viewBox="0 0 100 100">
            <path :d="pathString" :stroke="trailColor" :stroke-width="trailWidth" :fill-opacity="0"/>
            <path :d="pathString" :stroke-linecap="strokeLinecap" :stroke="strokeColor" :stroke-width="strokeWidth" fill-opacity="0" :style="pathStyle"/>
            <path class="ifHover" :d="pathString" :stroke-linecap="strokeLinecap" :stroke="strokeColor" :stroke-opacity="0.2" :stroke-width="hoverWidth" fill-opacity="0" :style="pathStyle"/>
        </svg>
        <div :class="innerClasses">
            <slot></slot>
        </div>
    </div>
</template>
<script>
    import { oneOf } from '../../utils/assist';

    const prefixCls = 'bsc-chart-circle';

    export default {
        name: 'iCircle',
        props: {
            percent: {
                type: Number,
                default: 0
            },
            size: {
                type: Number,
                default: 120
            },
            strokeWidth: {
                type: Number,
                default: 6
            },
            strokeColor: {
                type: String,
                default: '#2db7f5'
            },
            strokeLinecap: {
                validator (value) {
                    return oneOf(value, ['square', 'round']);
                },
                default: 'round'
            },
            trailWidth: {
                type: Number,
                default: 5
            },
            trailColor: {
                type: String,
                default: '#eaeef2'
            },
            hoverBorder: {
                type: Number,
                default: 2
            },
        },
        computed: {
            hoverWidth () {
                return (this.strokeWidth + this.hoverBorder * 2);
            },
            circleSize () {
                return {
                    width: `${this.size + this.hoverBorder * 2}px`,
                    height: `${this.size + this.hoverBorder * 2}px`
                };
            },
            radius () {
                return 50 - this.strokeWidth / 2 - this.hoverBorder;
            },
            pathString () {
                return `M 50,50 m 0,-${this.radius}
                a ${this.radius},${this.radius} 0 1 1 0,${2 * this.radius}
                a ${this.radius},${this.radius} 0 1 1 0,-${2 * this.radius}`;
            },
            len () {
                return Math.PI * 2 * this.radius;
            },
            pathStyle () {
                return {
                    'stroke-dasharray': `${this.len}px ${this.len}px`,
                    'stroke-dashoffset': `${((100 - this.percent) / 100 * this.len)}px`,
                    'transition': 'stroke-dashoffset 0.6s ease 0s, stroke 0.6s ease'
                };
            },
            wrapClasses () {
                return `${prefixCls}`;
            },
            innerClasses () {
                return `${prefixCls}-inner`;
            }
        }
    };
</script>
