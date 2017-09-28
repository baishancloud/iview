<p align="center">
    <a href="https://www.iviewui.com">
        <img width="200" src="https://file.iviewui.com/logo.svg">
    </a>
</p>

# iView
[![](https://img.shields.io/travis/iview/iview.svg?style=flat-square)](https://travis-ci.org/iview/iview)
[![iView](https://img.shields.io/npm/v/iview.svg?style=flat-square)](https://www.npmjs.org/package/iview)
[![NPM downloads](http://img.shields.io/npm/dm/iview.svg?style=flat-square)](https://npmjs.org/package/iview)
[![NPM downloads](https://img.shields.io/npm/dt/iview.svg?style=flat-square)](https://npmjs.org/package/iview)
![JS gzip size](http://img.badgesize.io/https://unpkg.com/iview/dist/iview.min.js?compression=gzip&label=gzip%20size:%20JS&style=flat-square)
![CSS gzip size](http://img.badgesize.io/https://unpkg.com/iview/dist/styles/iview.css?compression=gzip&label=gzip%20size:%20CSS&style=flat-square)
[![Join the chat at https://gitter.im/iview/iview](https://img.shields.io/badge/chat-on_gitter-30b392.svg?style=flat-square)](https://gitter.im/iview/iview?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

### A high quality UI Toolkit built on Vue.js.

> This branch is for Vue.js 2.x.
>
> The branch for Vue.js 1.x can be found [here](https://github.com/iview/iview/tree/master).
# iview-bsc

## Notes

- 将本地 ssh 密钥(~/.ssh/id_rsa.pub)添加到 github 的设置中 
- 拉取代码，使用 ssh 的方式
- 安装项目依赖并启动开发环境 (npm run dev, 其他命令查看 package.json)
- 发布更新: npm run prepublish => npm publish --registry http://registry.npmjs.org

控件源码在 src\ 目录下，如果新增控件需要在index 中引入，examples\ 下的文件是开发测试用，可以根据开发测试需求随便改(不需提交)

## Docs

### [中文文档 (2.0)](https://www.iviewui.com)
[中文文档 (1.0)](http://v1.iviewui.com)

## Overview

### [Component Overview](https://www.iviewui.com/overview)

## Features

- Dozens of useful and beautiful components.
<<<<<<< HEAD
- Friendly API. It's made for people with any skill level.
- Extensive documentation and demos.
- It is quite beautiful.
- Supports both Vue.js 2 and Vue.js 1.

## Who's using iView

- [TalkingData](http://www.talkingdata.com/)
- [Alibaba](http://www.alibaba.com/)
- [JD](http://www.jd.com/)
- [DiDi](http://www.didichuxing.com/)
- [Sina](http://www.sina.com.cn/)
- [Lenovo](https://www.lenovo.com.cn/)

> If your company or products use iView, welcome to click [here](https://github.com/iview/iview/issues/2143) to leave a message.

## Install

> Please install Webpack first!

We recommend you create your project through [iView Cli](https://github.com/iview/iview-cli) or [iview-project](https://github.com/iview/iview-project). You can also use [vue-cli](https://github.com/vuejs/vue-cli).
=======
- Friendly API. It's made for people with all skill levels.
- Extensive documentation and demos.
- It is quite beautiful.
- Supports Vue.js 2 and Vue.js 1.

## Install

> Please install Webpack first

We recommend you install project through [iView Cli](https://github.com/iview/iview-cli) Or [iview-project](https://github.com/iview/iview-project). You can also use [vue-cli](https://github.com/vuejs/vue-cli).
>>>>>>> Squashed commit of the following:

### Install iView

Using npm:
```
npm install iview --save
```
<<<<<<< HEAD

Using a script tag for global use:
=======
Or using script tag for global use
>>>>>>> Squashed commit of the following:

```html
<script type="text/javascript" src="iview.min.js"></script>
<link rel="stylesheet" href="dist/styles/iview.css">
```

<<<<<<< HEAD
You can find more info [on the website](https://www.iviewui.com/docs/guide/install-en).
=======
More info [in the website](https://www.iviewui.com/docs/guide/install-en)
>>>>>>> Squashed commit of the following:

## Usage

```vue
<template>
    <Slider v-model="value" range />
</template>
<script>
    export default {
        data () {
            return {
                value: [20, 50]
            }
        }
    }
</script>
```

Using css via `import`:

```js
import 'iview/dist/styles/iview.css';
```

## Compatibility

<<<<<<< HEAD
- Supports Vue.js 2.x
- Supports Vue.js 1.x - [visit 1.0 docs](http://v1.iviewui.com/)
- Supports SSR
- Supports [Nuxt.js](https://nuxtjs.org/)
- Supports [Electron](http://electron.atom.io/)
- iView does not support IE8 or below since [Vue.js](https://vuejs.org/v2/guide/reactivity.html) uses `Object.defineProperty` to track changes which is not supported by these browsers.

## Community

If you want to contribute or have questions or bugs to report:

**Questions:** Find other users at the [Gitter chat](https://gitter.im/iview/iview) or post on [StackOverflow using `[iview-ui]` tag](https://stackoverflow.com/questions/tagged/iview-ui)  
**Bugs:** [File a issue here](https://github.com/iview/iview/issues) - please provide a example so we can help you better  
**Contribute:** Contact us in [Gitter chat](https://gitter.im/iview/iview), WeChat or via mail to `admin@aresn.com`. PRs welcome!
=======
- Support Vue.js 2.x
- Support Vue.js 1.x [Visit 1.0 doc](http://v1.iviewui.com/)
- Support SSR
- Support [Nuxt.js](https://nuxtjs.org/)
- [Electron](http://electron.atom.io/)
- iView does not support IE8 or below since [Vue.js](https://vuejs.org/v2/guide/reactivity.html) is using Object.defineProperty which do not be supported by these browsers to track changes.

## Community

If you want to contribute, have questions or bugs to report:

**Questions:** you can find other users at [Gitter chat](https://gitter.im/iview/iview) or post on [StackOverflow using `[iview-ui]` tag](https://stackoverflow.com/questions/tagged/iview-ui)  
**Bugs:** [file a issue here](https://github.com/iview/iview/issues) and please provide a example so we can help you better  
**Contribute:** welcome to contact us in [Gitter chat](https://gitter.im/iview/iview), WeChat or via mail to `admin@aresn.com`. PRs welcome!
>>>>>>> Squashed commit of the following:

## Major Contributors
|Name|Avatar|Name|Avatar|Name|Avatar|
|---|---|---|---|---|---|
|[Aresn](https://github.com/icarusion) |  ![](https://avatars3.githubusercontent.com/u/5370542?v=3&s=60)  |[jingsam](https://github.com/jingsam) |  ![](https://avatars3.githubusercontent.com/u/1522494?v=3&s=60)  | [rijn](https://github.com/rijn)       |  ![](https://avatars2.githubusercontent.com/u/6976367?v=3&s=60)  |
|[lcx960324](https://github.com/lcx960324)           |  ![](https://avatars3.githubusercontent.com/u/9768245?v=3&s=60)  |[GITleonine1989](https://github.com/GITleonine1989) |  ![](https://avatars1.githubusercontent.com/u/7582490?v=3&s=60)  |[huixisheng](https://github.com/huixisheng)         |  ![](https://avatars1.githubusercontent.com/u/1518967?v=3&s=60)  |
|[Sergio Crisostomo](https://github.com/SergioCrisostomo)           |  ![](https://avatars3.githubusercontent.com/u/5614559?v=3&s=60)  |  [lison16](https://github.com/lison16)           |  ![](https://avatars3.githubusercontent.com/u/20942571?v=3&s=60) |  [Xotic750](https://github.com/Xotic750)    | ![](https://avatars3.githubusercontent.com/u/216041?v=3&s=60)


## Links

- [TalkingData](https://github.com/TalkingData)
- [Vue](https://github.com/vuejs/vue)
- [Webpack](https://github.com/webpack/webpack)
- [Ionicons](https://github.com/driftyco/ionicons)
- [Ant Design](https://github.com/ant-design/ant-design)

## License
[MIT](http://opensource.org/licenses/MIT)

Copyright (c) 2016-present, iView
