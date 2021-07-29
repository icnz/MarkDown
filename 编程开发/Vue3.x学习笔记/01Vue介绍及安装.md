### Vue.js 是什么

Vue (读音 /vjuː/，类似于 **view**) 是一套用于构建用户界面的**渐进式框架**。Vue 被设计为可以自底向上逐层应用。其核心库只关注视图层，便于与第三方库或既有项目整合。

Vue.js 的核心是一个允许采用简洁的模板语法来声明式地将数据渲染进 DOM 的系统：

```vue
// HTML:
<div id="counter">
  Counter: {{ counter }}
</div>
 // JS:
const Counter = {
  data() {
    return {
      counter: 0
    }
  }
};
Vue.createApp(Counter).mount('#counter');
```

### 安装

##### 1、CDN或自托管方式

对于生产环境，推荐链接到一个明确的版本号和构建文件，以避免新版本造成的不可预期的破坏。

也可以下载相关 .js 文件并自行托管在自己的服务器上。然后通过 <script> 标签引入。

```html
<script src="https://unpkg.com/vue@next"></script>
```

##### 2、npm方式

在用 Vue 构建大型应用时推荐使用 npm 安装。npm 能很好地和诸如 webpack 或 Rollup 模块打包器配合使用。

```shell
# 最新稳定版
$ npm install vue@next
# 编写单文件组件的配套工具
$ npm install -D @vue/compiler-sfc
```

##### 3、命令行工具 (CLI)方式

使用 Vue CLI 可创建一个配置最小化的 webpack 构建。它为现代前端工作流提供了功能齐备的构建设置。只需要几分钟的时间就可以运行起来并带有热重载、保存时 lint 校验，以及生产环境可用的构建版本。更多可查阅[Vue CLI 文档](https://cli.vuejs.org/zh/)。

```shell
yarn global add @vue/cli
# OR
npm install -g @vue/cli
```

然后在 Vue 项目中运行：

```shell
vue upgrade --next
```

##### 4、Vite方式

Vite 是一个 web 开发构建工具，由于其原生 ES 模块导入方式，可以实现闪电般的冷服务器启动。

```shell
# npm:
npm init vite <project-name> -- --template vue
cd <project-name>
npm install
npm run dev

#yarn:
yarn create vite <project-name> --template vue
cd <project-name>
yarn
yarn dev
```

### Vue Devtools

在使用 Vue 时，在浏览器上安装 Vue Devtools，可以在更友好的界面中审查和调试 Vue 应用。

[获取 Chrome 扩展程序](https://chrome.google.com/webstore/detail/vuejs-devtools/ljjemllljcmogpfapbkkighbhhppjdbg)   [获取 Firefox 附加组件](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)   [获取独立的 Electron 应用程序](https://github.com/vuejs/vue-devtools/blob/dev/packages/shell-electron/README.md)

