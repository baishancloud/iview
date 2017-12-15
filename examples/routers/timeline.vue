<style scoped>
    .time{
        font-size: 14px;
        font-weight: bold;
    }
    .content{
        padding-left: 5px;
    }
</style>
<template>
<div>
    <Timeline>
        <Timeline-item>
            <span slot="before">2017.03.18</span>
            <p class="content">Apple I 问世</p>
        </Timeline-item>
        <Timeline-item>
            <span slot="before">2017.03.18</span>
            <p class="content">发布 Macintosh</p>
        </Timeline-item>
        <Timeline-item>
            <span slot="before">2017.03.18</span>
            <p class="content">发布 iPhone</p>
        </Timeline-item>
        <Timeline-item>
            <p class="content">发布 iPad</p>
        </Timeline-item>
        <Timeline-item>
            <p class="content">史蒂夫·乔布斯去世</p>
        </Timeline-item>
    </Timeline>
    <Timeline>
        <Timeline-item color="green">
            <span slot="before">2017.03.18</span>发布1.0版本</Timeline-item>
        <Timeline-item color="green">
            <span slot="before">2017.03.18</span>发布2.0版本</Timeline-item>
        <Timeline-item color="red">严重故障</Timeline-item>
        <Timeline-item color="blue">发布3.0版本</Timeline-item>
    </Timeline>
    <Timeline pending>
        <Timeline-item>
            <span slot="before">2017.03.18</span>发布1.0版本</Timeline-item>
        <Timeline-item>
            <span slot="before">2017.03.18</span>发布2.0版本</Timeline-item>
        <Timeline-item>发布3.0版本</Timeline-item>
        <Timeline-item><a href="#">查看更多</a></Timeline-item>
    </Timeline>
    <Timeline>
        <Timeline-item color="green">
             <span slot="before">2017-03-18</span>
            <Icon type="trophy" slot="dot"></Icon>
            <span>发布里程碑版本</span>
        </Timeline-item>
        <Timeline-item>发布1.0版本</Timeline-item>
        <Timeline-item>发布2.0版本</Timeline-item>
        <Timeline-item>发布3.0版本</Timeline-item>
    </Timeline>
</div>
</template>
<script>
    export default {

    }
</script>
