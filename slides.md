---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: false
drawings:
  persist: false
transition: slide-left
title: 跨平台开发 
download: true
exportFilename: '跨平台开发'
---

# 跨平台开发uni-app
uni-app
---
transition: fade-out
---

# 跨平台开发的诞生
<v-clicks>

- 原生App存在的问题：
  - 开发时间长
  - 成本高
  - 迭代慢
  - 部署慢
  - 不利于推广等
  - 因此**一套代码，多端运行**的跨平台诞生

</v-clicks>

---

# 原生 VS 跨平台
<v-clicks>

- 原生开发模式的特点
  - 优点：**性能稳定，用户体验好，安全性高，兼容性好**，可使用手机所有硬件等。
  - 缺点：开发周期长，维护成本高，迭代慢，部署慢，新版本必须更新应用。不支持跨平台，必须同时开发多端代码。
  
- 跨平台开发的特点
  - 优点：**一套代码，多端运行。** 开发成本低，周期短。
  - 缺点：适用于和硬件交互少，业务不太复杂的项目。不适合做高性能、用户体验复杂的应用程序。同时开发多端兼容和适配比较麻烦、调试起来不方便。

</v-clicks>

---
transition: slide-up
---

# 认识uni-app
<v-clicks>

- <mark>uni-app</mark>是一个使用 <mark>[Vue.js](https://vuejs.org/) </mark>开发所有前端应用的框架，**开发者编写一套代码，可发布到iOS、Android、Web（响应式）、以及各种小程序**（微信/支付宝/百度/头条/飞书/QQ/快手/钉钉/淘宝）、快应用等多个平台。
  
<div class="mt10 flex justify-between content-start" >

- **为什么要选择uni-app？**
  - 开发者/案例数量更多
  - 平台能力不受限
  - 性能体验优秀
  - 周边生态丰富
  - 学习成本低
  - 开发成本低
  
<img class="w90" src="/uniapp.png" />
</div>
  
</v-clicks>
---

# 认识uni-app

<img class="h-105" src="/uniapp-framework.png" />

---

# uni-app VS 微信小程序
<v-clicks>

- 相同点
  - 接近**原生的体验、打开即用、不需要安装应用**
  - 有完善的官方文档
  - 生态圈丰富、组件丰富
  - 学习成本低
  
- 不同点
  - uni-app 支持跨平台，微信小程序不支持
  - uni-app 纯Vue体验、高效工程化强；微信小程序工程化弱，使用程序开发语言
  - uni-app 适合不太复杂的应用；微信小程序的兼容性和稳定性更好

</v-clicks>

---
layout: two-cols
---

# 创建uni-app项目

- uni-app 支持两种方式创建项目：
   
  - **1.通过 HBuilderX 创建** 
    - 下载安装 HbuilderX 编辑器 HBuilderX：[官方IDE下载地址](https://www.dcloud.io/hbuilderx.html)
    - 安装 uni-app vue3 编译器插件
    - 编译成微信小程序端代码
    - 开启服务端口

::right::

<div class="mt-16 ml-4">

![HbuilderX](HbuilderX.png)

</div>

---

# 创建uni-app项目

<v-clicks>

  - **2.通过命令行创建（不必依赖 HBuilderX）**
    - 使用正式版（对应HBuilderX最新正式版）
      ```bash
      vue create -p dcloudio/uni-preset-vue 项目名称
      ```

    - Vue3 + Vite + Typescript版:
      ```bash
      npx degit dcloudio/uni-preset-vue#vite-ts 项目名称
      ```
    - PS: **Vue3/Vite版要求 node 版本^14.18.0 || >=16.0.0**
    - [官网链接](https://uniapp.dcloud.net.cn/quickstart-cli.html#创建uni-app)

</v-clicks>

---

# 项目介绍

<div class="overflow-auto h-100">
<v-click>

```bash{16|17|18|all}
├── .husky                     # Git Hooks
├── dist                       # 打包文件夹（可删除重新打包）
├── src                        # 源代码
│   ├── components             # 全局组件
│   ├── pages                  # 主包页面
│       ├── index               # 首页
│   ├── services               # 所有请求
│   ├── static                 # 存放应用引用的本地静态资源的目录(ps:静态资源只能存放于此)
│   ├── stores                 # 全局 pinia store
│       ├── modules             # 模块
│       └── index.ts            # store 入口
│   ├── styles                 # 全局样式
│   ├── types                  # 类型声明文件
│   ├── utils                  # 全局方法
│   ├── App.vue                # 入口页面
│   ├── main.ts                # Vue初始化入口文件
│   ├── pages.json             # 配置页面路由、导航条、选项卡等页面类信息
│   ├── manifest.json          # 配置应用名称、appid、logo、版本等打包信息
│   └── uni.scss               # uni-app 内置的常用样式变量
├── .editorconfig              # editorconfig 配置
├── .eslintrc.cjs              # eslint 配置
├── .prettierrc.json           # prettier 配置
├── .gitignore                 # git 忽略文件
├── index.html                 # H5 端首页
├── package.json               # package.json 依赖
├── tsconfig.json              # typescript 配置
└── vite.config.ts             # vite 配置
```
</v-click>
</div>

---

# 组件


- [内置组件](https://uniapp.dcloud.net.cn/component/view.html)
- [扩展组件（uni-ui）](https://uniapp.dcloud.net.cn/component/view.html)：uni-ui是DCloud提供的一个跨端ui库，它是基于vue组件的、flex布局的、无dom的跨全端ui框架，它是**内置组件的补充**。
- [easycom](https://uniapp.dcloud.net.cn/collocation/pages.html#easycom): **HBuilderX 2.5.5**起支持**easycom**组件模式。


```json
// pages.json
{
  // 组件自动引入规则 修改easycom，需要重启服务器
  "easycom": {
    // 是否开启自动扫描
    "autoscan": true,
    // 以正则方式自定义组件匹配规则
    "custom": {
      // uni-ui 规则如下配置
      "^uni-(.*)": "@dcloudio/uni-ui/lib/uni-$1/uni-$1.vue",
      // 自动导入一以mp开头的组件
      "^Mp(.*)":"@/components/Mp$1.vue"
    }
  },
}
```

<style>
  img{
    width:40%;
  }
</style>

---
layout: two-cols
---

# 用VSCode开发uni-app

- **为什么选择 VSCode ？** 
  - 对 TS 类型支持暂不完善 
  - VSCode 对 TS 类型支持友好，熟悉的编辑器
  
- **VScode 安装uni-app插件**
  - **uni-create-view** ：快速创建 uni-app 页面
  - **uni-helper** ：uni-app 代码提示
  - **uniapp 小程序扩展** ：鼠标悬停查文档
  
::right::

<div class="mt-16 ml-30">

<img class="w70" src="/vscodePlugin.png" />"

</div>

---

# 用VSCode开发uni-app
<v-click>

- ts 类型校验
  - 安装类型声明文件:
    ```bash
    npm i -D @types/wechat-miniprogram @uni-helper/uni-app-types
    ```

  - 配置 tsconfig.json
  
  <div class="overflow-auto h-60">

  ```json
      {
        "compilerOptions": {
          "types": [
            "@dcloudio/types",
            "miniprogram-api-typings",
            "@uni-helper/uni-app-types",
            "@uni-helper/uni-ui-types"
          ]
        },
        "vueCompilerOptions": {
          // experimentalRuntimeMode 已废弃，现调整为 nativeTags，请升级 Volar 插件至最新版本
          "nativeTags": ["block", "component", "template", "slot"]
        },
      }
    ```
  </div>

</v-click>

---

# 用VSCode开发uni-app
<v-click>

- json 注释问题
![jsonc](/jsonc.png)

</v-click>

---

# 微信开发者工具调试

- HBuilderX
  - Tool -> Setting -> Run -> WeChat Developer Runing Configuration
  
- VScode
  - 执行 ```npm run dev:mp-weixin```
  - 打开微信开发者工具, 导入此路径 **dist\dev\mp-weixin** 下的代码包 
---

# 项目打包

- **微信小程序**
  ```bash
  npm run build:mp-weixin
  ```
  - 发布
    1. 打开微信开发者工具，导入 **dist\build\mp-weixin** 代码包，并上传代码；
    2. 微信公众号后台提交审核。
   
- **H5**
  ```bash
  npm run build:h5
  ```

- **Android & IOS**
  - 如果打包成 App 端，将项目代码导入 HbuilderX 开发工具，由 HbuilderX 运行到真机或模拟器，提供原生App云打包服务。  
---

# 跨端兼容
- **条件编译**
  - 条件编译语法：通过特殊注释，以 **#ifdef** 或 **#ifndef** 加 平台名称 开头，以 **#endif** 结尾。

- **样式兼容**
  - 非H5端不支持*选择器
  - 非H5端默认并未启用 scoped
  - 页面**视口差异**
  - [uni-app跨端注意](https://uniapp.dcloud.net.cn/matter.html)

---

# 跨端兼容

- **组件兼容**
  
  例如：[button](https://uniapp.dcloud.net.cn/component/button.html) 
  ![buttonType](/buttonType.png)

  ![buttonOpenType](/buttonOpenType.png)

<style>
  img{
    max-width:65%;
  }
</style>

---

# 跨端兼容

- JSAPI兼容
  - 非H5端，不支持window、document等浏览器的JSAPI。
  
---

# 骨架屏

<div class="flex justify-between content-start">

- 微信开发者工具 -> 生成骨架屏 -> 转成vue文件 -> 展示骨架屏

<img class="w50" src="/skeleton.png"/>

</div>

---
layout: end
---


<style>
  .end {
    background: url('https://source.unsplash.com/collection/94734566/1920x1080') no-repeat center center;
    background-size: cover;
    font-size: 2.5rem !important;
  } 
</style>
