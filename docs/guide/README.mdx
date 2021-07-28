---
---

import useBaseUrl from '@docusaurus/useBaseUrl'

# EMP - Micro Frontends solution

> Base on Webpack 5 & Module Federation

English | [Discussions](https://github.com/efoxTeam/emp/discussions)

An implementation of [Micro Frontends](https://micro-frontends.org/), based on [Webpack5 Module Federation](https://webpack.js.org/concepts/module-federation/), but made it production-ready.

## 👨🏻‍💻 Table of contents

- [Projects](https://github.com/efoxTeam/emp#-projects)
- [Documentation](https://github.com/efoxTeam/emp#-documentation)
- [Quick Overview](https://github.com/efoxTeam/emp#-quick-overview)
- [Command plugin development guide](https://github.com/efoxTeam/emp#%EF%B8%8F-command-plugin-development-guide)
- [Framework Config Plugins](https://github.com/efoxTeam/emp#-framework-config-plugins)
- [EMP multi-frame intermodulation conversion plug-in](https://github.com/efoxTeam/emp#-emp-multi-frame-intermodulation-conversion-plug-in)
- [Demos](https://github.com/efoxTeam/emp#-demos)
- [Use multiple frameworks in EMP Application](https://github.com/efoxTeam/emp#-use-multiple-frameworks-in-emp-application)
- [Community](https://github.com/efoxTeam/emp#-community)

## 📦 Projects

| Project                                                                                                                     | NPM                                                                                                                                                       | Info                                                       |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| [@efox/emp-cli](https://github.com/efoxTeam/emp/tree/main/packages/emp-cli)                                                 | [![release](https://img.shields.io/npm/v/@efox/emp-cli.svg)](https://www.npmjs.com/package/@efox/emp-cli)                                                 | CLI                                                        |
| [@efox/emp-tsconfig](https://github.com/efoxTeam/emp/tree/main/packages/emp-tsconfig)                                       | [![release](https://img.shields.io/npm/v/@efox/emp-tsconfig.svg)](https://www.npmjs.com/package/@efox/emp-tsconfig)                                       | Typescript Config                                          |
| [@efox/emp-tune-dts-plugin](https://github.com/efoxTeam/emp/tree/main/packages/emp-tune-dts-plugin)                         | [![release](https://img.shields.io/npm/v/@efox/emp-tune-dts-plugin.svg)](https://www.npmjs.com/package/@efox/emp-tune-dts-plugin)                         | Webpack Plugin for Module Federation Project in Typescript |
| [@efox/eslint-config-react-prittier-ts](https://github.com/efoxTeam/emp/tree/main/packages/eslint-config-react-prittier-ts) | [![release](https://img.shields.io/npm/v/@efox/eslint-config-react-prittier-ts.svg)](https://www.npmjs.com/package/@efox/eslint-config-react-prittier-ts) | ESLint Config                                              |
| [@efox/emp-sync-vscode-plugin](https://github.com/efoxTeam/emp-sync-vscode-plugin)                                          | [![release](https://img.shields.io/badge/emp--sync--base-v0.1.5-green.svg)](https://marketplace.visualstudio.com/items?itemName=Benny.emp-sync-base)      | EMP Type Synchronize VSCode Plugin                         |

## 📖 Documentation

[https://github.com/efoxTeam/emp/wiki](https://github.com/efoxTeam/emp/wiki)

## 💿 Quick Overview

```sh
npx @efox/emp-cli init
cd my-emp && yarn && yarn dev
```

- If you've previously installed `@efox/emp-cli`,globally via `npm install -g @efox/emp-cli` or `yarn global add @efox/emp-cli `.
- we recommend you uninstall the package using `npm uninstall -g @efox/emp-cli` or `yarn global remove @efox/emp-cli` to ensure that npx always uses the latest version.

- run `cd my-emp && yarn && yarn dev`,the project will automatically open in the browser.

- If you want to know more about the use of `@efox/emp-cli`, go to [emp-cli](https://github.com/efoxTeam/emp/tree/main/packages/emp-cli).

<img
  src={useBaseUrl('/assets/init.gif')}
  width="600"
  alt="npx @efox/emp-cli init"
/>

## 🧞‍♂️ Command plugin development guide

- command - define the name of the command line command
- description - description, it will be shown in help
- option - Define parameters. It accepts four parameters. In the first parameter, it can enter the short name -a and the long name -app, separated by | or,. When used on the command line, these two are equivalent. The difference is The latter can be obtained through callbacks in the program; the second is the description, which will be displayed in the help message; the third parameter is the callback function, and the parameter it receives is a string. Sometimes we need a command line to create multiple Module, you need a callback to process; the fourth parameter is the default value
- action - Register a callback function, here you need to pay attention to the current callback does not support let declaration variables

### plugin, the package name prefix needs to be `emp-plugin-*`, `cli.js` is the emp global plugin entry.

- Create a new project with `emp-plugin-` as the project prefix, and the plugin entry is `cli.js`

```javascript
module.exports = (program) => {
  program
    .command('helloWorldPlugin')
    .option('-i, --item <item>')
    .description([`It is plugin description`])
    .action(({ item }) => {
      console.log(`Plugin ${item}`)
    })
}
```

- After the development is completed (emp-plugin-example is only the example package name, the specific package name is subject to the actual package name):
- Install via `yarn`:
  - `yarn global add emp-plugin-example`
- Install via `npm`:
  - `npm install emp-plugin-example -g`

Start emp under the command to use the plugin<br />

<img
  src="https://user-images.githubusercontent.com/19996552/113428029-a55e4500-9408-11eb-906d-29795199f422.png"
  width="600"
  alt="npx @efox/emp-cli init"
/>
<br />

## ✨ Framework Config Plugins

| Framework | NPM                                                                                                              | demo                                                                 | project                                                                                       | install                         |
| --------- | ---------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------- |
| react     | [![release](https://img.shields.io/npm/v/@efox/emp-react.svg)](https://www.npmjs.com/package/@efox/emp-react)    | [demo](https://github.com/efoxTeam/emp/tree/main/projects/react)     | [@efox/emp-react]https://github.com/efoxTeam/emp/tree/main/packages/emp-frameworks/react)     | `yarn add @efox/emp-react -D`   |
| vue2      | [![release](https://img.shields.io/npm/v/@efox/emp-vue2.svg)](https://www.npmjs.com/package/@efox/emp-vue2)      | [demo](https://github.com/efoxTeam/emp/tree/main/projects/vue2)      | [@efox/emp-vue2]https://github.com/efoxTeam/emp/tree/main/packages/emp-frameworks/vue2)       | `yarn add @efox/emp-vue2 -D`    |
| vue3      | [![release](https://img.shields.io/npm/v/@efox/emp-vue3.svg)](https://www.npmjs.com/package/@efox/emp-vue3)      | [demo](https://github.com/efoxTeam/emp/tree/main/projects/vue3-base) | [@efox/emp-vue3]https://github.com/efoxTeam/emp/tree/main/packages/emp-frameworks/vue3)       | `yarn add @efox/emp-vue3 -D`    |
| svelte    | [![release](https://img.shields.io/npm/v/@efox/emp-svetle.svg)](https://www.npmjs.com/package/@efox/emp-svetle)  | [demo](https://github.com/efoxTeam/emp/tree/main/projects/svelte)    | [@efox/emp-svelte]https://github.com/efoxTeam/emp/tree/main/packages/emp-frameworks/svelte)   | `yarn add @efox/emp-svetle -D`  |
| preact    | [![release](https://img.shields.io/npm/v/@efox/emp-svetle.svg)](https://www.npmjs.com/package/@efox/emp-preact)  | [demo](https://github.com/efoxTeam/emp/tree/main/projects/preact)    | [@efox/emp-preact]https://github.com/efoxTeam/emp/tree/main/packages/emp-frameworks/preact)   | `yarn add @efox/emp-preact -D`  |
| cocos2d   | [![release](https://img.shields.io/npm/v/@efox/emp-cocos2d.svg)](https://www.npmjs.com/package/@efox/emp-preact) | [demo](https://github.com/efoxTeam/emp/tree/main/projects/cocos2d)   | [@efox/emp-cocos2d]https://github.com/efoxTeam/emp/tree/main/packages/emp-frameworks/cocos2d) | `yarn add @efox/emp-cocos2d -D` |

## ⚡ Compile

| Framework                  | NPM                                                                                                         | demo                                                                                                                                                      | install                  |
| -------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ |
| [emp-swc](https://swc.rs/) | [![release](https://img.shields.io/npm/v/@efox/emp-swc.svg)](https://www.npmjs.com/package/@efox/emp-vuett) | [plugin]https://github.com/efoxTeam/emp/tree/main/packages/emp-compile/swc) [react-demo](https://github.com/efoxTeam/emp/tree/main/projects/swc-react-ts) | `yarn add @efox/emp-swc` |

## ⚡ EMP multi-frame intermodulation conversion plug-in

| Framework        | NPM                                                                                                           | demo                                                                    | install                    |
| ---------------- | ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- | -------------------------- |
| emp-vue2-in-vue3 | [![release](https://img.shields.io/npm/v/@efox/emp-vuett.svg)](https://www.npmjs.com/package/@efox/emp-vuett) | [demo](https://github.com/efoxTeam/emp/tree/main/projects/vue3-project) | `yarn add @efox/emp-vuett` |

## 📦 Demos

| Framework                                                  | demo                                                                                                                                                                  | cli                                     |
| ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| <img src={useBaseUrl('/assets/react.png')} width='38'/>    | [react-demo1](https://github.com/efoxTeam/emp/tree/main/projects/demo1) [react-demo2](https://github.com/efoxTeam/emp/tree/main/projects/demo2)                       | `cd projects && yarn dev`               |
| <img src={useBaseUrl('/assets/vue.png')} width='38'/>      | [vue3-base](https://github.com/efoxTeam/emp/tree/main/projects/vue3-base) [vue3-project](https://github.com/efoxTeam/emp/tree/main/projects/vue3-project)             | `cd projects && yarn dev:vue`           |
| <img src={useBaseUrl('/assets/vue.png')} width='38'/>      | [vue2-base](https://github.com/efoxTeam/emp/tree/main/projects/vue2-base) [vue2-project](https://github.com/efoxTeam/emp/tree/main/projects/vue2-project)             | `cd projects && yarn dev:vue2`          |
| <img src={useBaseUrl('/assets/antd.jpeg')} width='38'/>    | [antd-base](https://github.com/efoxTeam/emp/tree/main/projects/antd-base) [antd-project](https://github.com/efoxTeam/emp/tree/main/projects/antd-project1)            | `cd projects && yarn dev:antd`          |
| <img src={useBaseUrl('/assets/preact.png')} height='38'/>  | [preact-base](https://github.com/efoxTeam/emp/tree/main/projects/preact-base) [preact-project](https://github.com/efoxTeam/emp/tree/main/projects/preact-project)     | `cd projects && yarn dev:preact`        |
| <img src={useBaseUrl('/assets/cocos2d.png')} height='38'/> | [cocos2d-base](https://github.com/efoxTeam/emp/tree/main/projects/cocos2d-base) [cocos2d-project](https://github.com/efoxTeam/emp/tree/main/projects/cocos2d-project) | `cd projects && yarn dev:cocos2d`       |
| <img src={useBaseUrl('/assets/https.png')} width='38'/>    | [https](https://github.com/efoxTeam/emp/tree/main/projects/https)                                                                                                     | `cd projects/https && yarn dev`         |
| <img src={useBaseUrl('/assets/dynamic.png')} height='38'/> | [dynamic-system-host](https://github.com/efoxTeam/emp/tree/main/projects/dynamic-system-host)                                                                         | `cd projects && yarn dev:dynamichost`   |
| <img src={useBaseUrl('/assets/dotenv.png')} height='38'/>  | [dotenv](https://github.com/efoxTeam/emp/tree/main/projects/empty-project/.env.prod)                                                                                  | `cd projects/empty-project && yarn dev` |

## 💪 Use multiple frameworks in EMP Application

| Framework                                                                                                      | demo                                                                                                                                                                  | cli                                 |
| -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------- |
| <img src={useBaseUrl('/assets/react.png')} width='38'/><img src={useBaseUrl('/assets/react.png')} width='38'/> | [React 16](https://github.com/efoxTeam/emp/tree/main/projects/react-diff16) & [React 17](https://github.com/efoxTeam/emp/tree/main/projects/react-diff17)             | `cd projects && yarn dev:reactdiff` |
| <img src={useBaseUrl('/assets/react.png')} width='38'/><img src={useBaseUrl('/assets/vue.png')} width='38'/>   | [Vue use React](https://github.com/efoxTeam/emp/tree/main/projects/reactVue-vue) & [React use Vue](https://github.com/efoxTeam/emp/tree/main/projects/reactVue-react) | `cd projects && yarn dev:reactvue`  |
| <img src={useBaseUrl('/assets/vue.png')} width='38'/><img src={useBaseUrl('/assets/vue.png')} width='38'/>     | [Vue3](https://github.com/efoxTeam/emp/tree/main/projects/vue23-vue2) & [Vue2](https://github.com/efoxTeam/emp/tree/main/projects/vue23-vue3)                         | `cd projects && yarn dev:vue23`     |

## 👬 Community

- WeChat Group：

<img
  src="https://user-images.githubusercontent.com/3890513/117619197-8a1dec80-b1a1-11eb-9bdc-ed3b4f5fa090.png"
  width="290"
/>

- WeChat Official Account： Efox

<img src={useBaseUrl('/assets/wechatLogo.jpg')} width="290" />

- Juejin：

https://juejin.cn/user/483440843559406/posts

- oschina:

https://my.oschina.net/u/568478
