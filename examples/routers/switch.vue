<template>
    <div>
        <i-switch :only-text="true">
            <span slot="open">开</span>
            <span slot="close">关</span>
        </i-switch>
        <i-switch>
            <span slot="open">开</span>
            <span slot="close">关</span>
        </i-switch>
        <i-switch disabled>
            <span slot="open">开</span>
            <span slot="close">关</span>
        </i-switch>
        <i-switch class="bsc-switch-only-text" disabled>
            <span slot="open">开</span>
            <span slot="close">关</span>
        </i-switch>
    </div>
</template>
<script>
    export default {
        data () {
            return {
            };
        },
        methods: {
        }
    };
</script>
