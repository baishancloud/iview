<!--<style>-->
    <!--.demo-spin-icon-load{-->
        <!--animation: ani-demo-spin 1s linear infinite;-->
    <!--}-->
    <!--@keyframes ani-demo-spin {-->
        <!--from { transform: rotate(0deg);}-->
        <!--50%  { transform: rotate(180deg);}-->
        <!--to   { transform: rotate(360deg);}-->
    <!--}-->
    <!--.demo-spin-col{-->
        <!--height: 100px;-->
        <!--position: relative;-->
        <!--border: 1px solid #eee;-->
    <!--}-->
    <!--/*loading*/-->
    <!--.loader{-->
        <!--width: 30px;-->
        <!--height: 30px;-->
        <!--position: relative;-->
        <!--margin: 0 auto;-->
    <!--}-->
    <!--.circular {-->
        <!-- -webkit-animation: rotate 2s linear infinite;-->
        <!--animation: rotate 2s linear infinite;-->
        <!--height: 100%;-->
        <!-- -webkit-transform-origin: center center;-->
        <!-- -ms-transform-origin: center center;-->
        <!--transform-origin: center center;-->
        <!--width: 100%;-->
        <!--position: absolute;-->
        <!--top: 0;-->
        <!--bottom: 0;-->
        <!--left: 0;-->
        <!--right: 0;-->
        <!--margin: auto;-->
    <!--}-->

    <!--.path {-->
        <!--stroke-dasharray: 1, 200;-->
        <!--stroke-dashoffset: 0;-->
        <!-- -webkit-animation: dash 1.5s ease-in-out infinite, color 6s ease-in-out infinite;-->
        <!--animation: dash 1.5s ease-in-out infinite, color 6s ease-in-out infinite;-->
        <!--stroke-linecap: round;-->
    <!--}-->
    <!--@-webkit-keyframes-->
    <!--rotate {  100% {-->
        <!-- -webkit-transform: rotate(360deg);-->
        <!--transform: rotate(360deg);-->
    <!--}-->
    <!--}-->
    <!--@keyframes-->
    <!--rotate {  100% {-->
        <!-- -webkit-transform: rotate(360deg);-->
        <!--transform: rotate(360deg);-->
    <!--}-->
    <!--}-->
    <!--@-webkit-keyframes-->
    <!--dash {  0% {-->
        <!--stroke-dasharray: 1, 200;-->
        <!--stroke-dashoffset: 0;-->
    <!--}-->
        <!--50% {-->
            <!--stroke-dasharray: 89, 200;-->
            <!--stroke-dashoffset: -35;-->
        <!--}-->
        <!--100% {-->
            <!--stroke-dasharray: 89, 200;-->
            <!--stroke-dashoffset: -124;-->
        <!--}-->
    <!--}-->
    <!--@keyframes-->
    <!--dash {  0% {-->
        <!--stroke-dasharray: 1, 200;-->
        <!--stroke-dashoffset: 0;-->
    <!--}-->
        <!--50% {-->
            <!--stroke-dasharray: 89, 200;-->
            <!--stroke-dashoffset: -35;-->
        <!--}-->
        <!--100% {-->
            <!--stroke-dasharray: 89, 200;-->
            <!--stroke-dashoffset: -124;-->
        <!--}-->
    <!--}-->
    <!--@-webkit-keyframes-->
    <!--color {  100%, 0% {-->
        <!--stroke: #d62d20;-->
    <!--}-->
        <!--40% {-->
            <!--stroke: #0057e7;-->
        <!--}-->
        <!--66% {-->
            <!--stroke: #008744;-->
        <!--}-->
        <!--80%, 90% {-->
            <!--stroke: #ffa700;-->
        <!--}-->
    <!--}-->
    <!--@keyframes-->
    <!--color {  100%, 0% {-->
        <!--stroke: #d62d20;-->
    <!--}-->
        <!--40% {-->
            <!--stroke: #0057e7;-->
        <!--}-->
        <!--66% {-->
            <!--stroke: #008744;-->
        <!--}-->
        <!--80%, 90% {-->
            <!--stroke: #ffa700;-->
        <!--}-->
    <!--}-->
<!--</style>-->
<!--<template>-->
    <!--<div>-->
        <!--<Row>-->
            <!--<i-col class="demo-spin-col" span="8">-->
                <!--<Spin fix>加载中...</Spin>-->
            <!--</i-col>-->
            <!--<i-col class="demo-spin-col" span="8">-->
                <!--<Spin fix>-->
                    <!--<Icon type="load-c" size=18 class="demo-spin-icon-load"></Icon>-->
                    <!--<div>Loading</div>-->
                <!--</Spin>-->
            <!--</i-col>-->
            <!--<i-col class="demo-spin-col" span="8">-->
                <!--<Spin fix>-->
                    <!--<div class="loader">-->
                        <!--<svg class="circular" viewBox="25 25 50 50">-->
                            <!--<circle class="path" cx="50" cy="50" r="20" fill="none" stroke-width="5" stroke-miterlimit="10"></circle>-->
                        <!--</svg>-->
                    <!--</div>-->
                <!--</Spin>-->
            <!--</i-col>-->
        <!--</Row>-->
    <!--</div>-->
<!--</template>-->
<!--<script>-->
    <!--// 部分样式代码冗长，未作展示-->
    <!--export default {-->

    <!--}-->
<!--</script>-->

<style>
    .demo-spin-article{
        /*width: 400px;*/
        /*height: 200px;*/
        padding: 10px;
        position: relative;
        border: 1px solid red;
        text-align: center;
        background-color: #39434b;
    }
    .demo-spin-article h3{
        font-size: 22px;
    }
    .demo-spin-article address{
        color: #999;
        font-style: normal;
        font-size: 14px;
    }
    .demo-spin-article p {
        font-size: 16px;
    }
</style>
<template>
    <div>
        <div class="demo-spin-article">
            <h3>登金陵凤凰台</h3>
            <address>李白</address>
            <article>
                <p>凤凰台上凤凰游，凤去台空江自流。</p>
                <p>吴宫花草埋幽径，晋代衣冠成古丘。</p>
                <p>三山半落青天外，二水中分白鹭洲。</p>
                <p>总为浮云能蔽日，长安不见使人愁。</p>
            </article>
            <Table border stripe :columns="columns6" :data="data5"></Table>
            <Spin size="large" fix v-if="spinShow">
                <!--<Icon type="load-c" size=18 class="demo-spin-icon-load"></Icon>-->
                <!--<div>Loading</div>-->
            </Spin>
        </div>
        <br>
        切换显示状态：<i-switch @on-change="spinShow = !spinShow"></i-switch>
        <Button @click="show">show</Button>
        <Button @click="hide">hide</Button>
    </div>
</template>
<script>
    export default {
        data () {
            return {
                spinShow: true,
                columns6: [
                    {
                        title: '日期',
                        key: 'date',
                        sortable: true
                    },
                    {
                        title: '姓名',
                        key: 'name'
                    },
                    {
                        title: '年龄',
                        key: 'age',
                        filters: [
                            {
                                label: '大于25岁',
                                value: 1
                            },
                            {
                                label: '小于25岁',
                                value: 2
                            }
                        ],
                        filterMultiple: false,
                        filterMethod (value, row) {
                            if (value === 1) {
                                return row.age > 25;
                            } else if (value === 2) {
                                return row.age < 25;
                            }
                        }
                    },
                    {
                        title: '地址',
                        key: 'address',
                        filters: [
                            {
                                label: '北京',
                                value: '北京'
                            },
                            {
                                label: '上海',
                                value: '上海'
                            },
                            {
                                label: '深圳',
                                value: '深圳'
                            }
                        ],
                        filterMethod (value, row) {
                            return row.address.indexOf(value) > -1;
                        }
                    }
                ],
                data5: [
                    {
                        name: '王小明',
                        age: 18,
                        address: '北京市朝阳区芍药居',
                        date: '2016-10-03'
                    },
                    {
                        name: '张小刚',
                        age: 25,
                        address: '北京市海淀区西二旗',
                        date: '2016-10-01'
                    },
                    {
                        name: '李小红',
                        age: 30,
                        address: '上海市浦东新区世纪大道',
                        date: '2016-10-02'
                    },
                    {
                        name: '周小伟',
                        age: 26,
                        address: '深圳市南山区深南大道',
                        date: '2016-10-04'
                    }
                ]
            }
        },
        methods: {
            show () {
                this.$Spin.show();
                setTimeout(() => {
                    this.$Spin.hide();
                }, 3000)
            },
            hide () {
                this.$Spin.hide();
            }
        }
    }
</script>
