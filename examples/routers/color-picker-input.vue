<template>
    <div style="margin: 100px;">
        {{ color }}
        <color-picker-input v-model="color" placement="bottom-start" size="large"></color-picker-input>
    </div>
</template>
<script>
    export default {
        props: {},
        data () {
            return {
                color: '#923456'
            };
        },
        computed: {},
        methods: {
        }
    };
</script>