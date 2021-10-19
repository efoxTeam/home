---
sidebar_label: 搭建第一个EMP项目
sidebar_position: 2
---

# 搭建第一个EMP项目

> 本文讲述的是项目中如何接入和使用emp（以react项目为例）。场景主要是两种, 第一种是通过@efox/emp-cli初始化新建项目（已默认接入），第二种就是现有的项目如何改造emp。

## 新建项目

### 首先了解一下emp命令

EMP维护了一套**cli脚手架**和一系列的**template模板**，可以让新手开箱使用。

首先我们可以全局安装[@efox/emp-cli](https://github.com/efoxTeam/emp/tree/main/packages/emp-cli)

```
yarn global add @efox/emp-cli
// or npm i -g @efox/emp-cli 
```

安装成功后，我们可以输入命令查看版本：
```
emp -v
```
![](/img/emp-v.png)

当然，我们也可以查看帮助更好了解emp命令的使用：

```
emp -h
```
![](/img/emp-h.png)

### 初始化两个应用项目

接下来，我们会在emp初始化的指引下，建立两个应用项目，分别命名为**react-base**和**react-project**，我们将体验两个项目之间如何进行资源共享。

我们先执行初始化指令，跟着命令的指引完成项目初始化，模板我们先选择**react-base**

```js
emp init
```
![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/80e3437de6de4d04929a31dbd102df8a~tplv-k3u1fbpfcp-watermark.image)
我们可以先看看**react-base**的目录：


![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bbac3810b4764a6c8469c1922681b980~tplv-k3u1fbpfcp-watermark.image)

其中重点关注的是**emp-config.js**这个文件。从这个文件中，我们可以看出使用了webpack的**mf**和**html**两个插件，我们先看**mf**插件的传参：

```
  config.plugin('mf').tap(args => {
    args[0] = {
      ...args[0],
      ...{
        // 项目名称
        name: 'empReactBase',
        // 被远程引入的文件名
        filename: 'emp.js',
        remotes: {
          // 远程项目别名:远程引入的项目名
          // ...
        },
        // 需要暴露的东西
        exposes: {
          // 别名:组件的路径
          './configs/index': 'src/configs/index',
          // ...
        },
        // 需要共享的依赖
        shared: {...dependencies},
      },
    }
    return args
  })
```
参数含义：

|  字段名   | 类型  |  含义  |
|  ----  | ----  | ----  |
| name  | string |项目名称，可以理解为应用的身份证，在应用分享资源时使用的标识应用唯一性的凭证 |
| filename  | string |构建后的chunk名称，也是被远程引入的文件名，可以理解为应用有了身份证还需要具体的入口地址才可以互相使用资源 |
| remotes  | object | 此处声明该应用想使用其他应用的什么资源，格式如：【远程项目别名:远程引入的项目名@远程引入的项目的emp.js】 |
| exposes  | object | 此处声明该应用可以分享出去什么资源，格式如【别名:组件的路径】 |
| shared  | object |需要共享的依赖，可以在这里控制第三包的版本号 |


看到这里，我们大概理解了**react-base**项目的**emp.config.js**文件是怎么配置想要其他应用的资源，以及如何分享出去自己的资源的，那么我们再初始化一个**react-project**项目来实践一下吧，记得选择**react-project**模板：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a354f73d5f50467ead33d006e8b19b02~tplv-k3u1fbpfcp-watermark.image)

我们对比**react-base**和**react-project**项目的配置，看到**react-base**在**emp.config.js**配置文件中声明分享了一个Hello组件：
```
exposes: {
  // 别名:组件的路径
  './components/Hello': 'src/components/Hello',
},
```

**react-project**在**emp.config.js**配置文件中声明需要使用**react-base**项目的Hello组件：

```
remotes: {
  // 远程项目别名:远程引入的项目名
  '@emp/react-base': 'empReactBase@http://localhost:8001/emp.js',
},
```

并且**react-project**在项目代码中，引入使用了**react-base**项目的Hello组件：

```
import HelloDEMO from '@emp/react-base/components/Demo'
const App = () => (
  <>
    // ...
     <HelloDEMO />
    // ...
  </>
)
```

那么，我们跟着指令分别跑起**react-base**和**react-project**项目来看Hello组件引入效果吧：
```
cd react-base && yarn && yarn dev
cd react-project && yarn && yarn dev
```
![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b57845694bb04472b7097d12533fbd2a~tplv-k3u1fbpfcp-watermark.image)

恭喜你跨入EMP微前端第一步！！！

应用之间可以分享的东西可多了，包括UI组件、函数甚至是应用，赶紧试试吧~

## 已有项目接入EMP

很多情况下，我们应用微前端希望是可以无缝接入现有项目的。那么，在现有的React项目中如何中途无缝接入EMP更真实感受EMP的魅力呢？我们一起来吧~

### 1. 修改package.json

我们可以根据上面**react-base**和**react-project**项目中的package.json，将其中的scripts命令按需添加进已有的项目：

```js
"scripts": {
    "dev": "emp dev",
    "dev:hot": "emp dev --hot",
    "build": "emp build",
    "build:ts": "emp build -t",
    "build:lab": "emp build --env lab",
    "tss": "emp tss http://localhost:8001/index.d.ts -n @emp-react-base.d.ts",
    "start": "emp serve",
    "analyze": "emp build --analyze"
},
```

### 2. 添加emp-config.js

我们在当前项目根目录下添加emp-config.js配置文件，内容也可以参考**react-base**和**react-project**项目，只要懂得了配置字段的含义，相信一点都不难：

```js
const path = require('path')
const packagePath = path.join(path.resolve('./'), 'package.json')
const {dependencies} = require(packagePath)
console.log(packagePath)

module.exports = ({config, env}) => {
  const port = 8003
  const projectName = 'projectName'
  const publicPath = `http://localhost:${port}/`
  config.plugin('mf').tap(args => {
    args[0] = {
      ...args[0],
      ...{
        // 项目名称
        name: projectName,
        // 被远程引入的文件名
        filename: 'emp.js',
        // 远程项目别名:远程引入的项目名
        remotes: {
          '@emp/react-base': 'empReactBase@http://localhost:8001/emp.js',
        },
        // 需要暴露的东西
        exposes: {
        },
        shared: {...dependencies},
      },
    }
    return args
  })
  config.output.publicPath(publicPath)
  config.devServer.port(port)
  config.plugin('html').tap(args => {
    args[0] = {
      ...args[0],
      ...{
        files: {
          js: ['http://localhost:8001/emp.js'],
        },
      },
    }
    return args
  })
}
```
### 3.添加入口文件

接着，可以在src目录下增加入口文件bootstrap.tsx和 index.ts。

其中index.ts文件内容如下：
```js
import('./bootstrap')
```
bootstrap.tsx内容如下：
```js
import React from 'react'
import ReactDOM from 'react-dom'
import App from 'src/view/index' //原来项目的入口文件
ReactDOM.render(<App />, document.getElementById('emp-root'))
```
### 4.使用共享资源

接下来，我们就可以在项目中引用远程组件了：
```js
import HelloDEMO from '@emp/react-base/components/Demo'
const App = () => (
  <>
    <HelloDEMO />
  </>
)
export default App
```
## 最后

在实际使用中，我们可能会遇到下面几点小问题：

1. 项目中如果使用了@别名，需要在emp-config.js增加以下代码
```js
  config.resolve.alias
    .set('@', path.resolve('./', 'src'))
```
2. 在webpack5中是默认没有node的core module，如果使用了这些核心库。需要在emp-config.js增加这些核心库，代码如下：
```js
  config.resolve.alias
    .set('zlib',"browserify-zlib")
    .set('assert', "assert")
    .set('buffer', "buffer")
    .set('util', "util")
    .set('stream', "stream-browserify")
    .set('timers', "timers-browserify")
```

