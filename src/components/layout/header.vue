<template>
    <div :class="wrapClasses"><slot></slot></div>
</template>
<script>
    const prefixCls = 'bsc-layout';
    export default {
        name: 'Header',
        computed: {
            wrapClasses () {
                return `${prefixCls}-header`;
            }
        }
    };
</script>