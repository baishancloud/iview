<template>
    <div :class="wrapClasses"><slot></slot></div>
</template>
<script>
    const prefixCls = 'bsc-layout';
    export default {
        name: 'Footer',
        computed: {
            wrapClasses () {
                return `${prefixCls}-footer`;
            }
        }
    };
</script>