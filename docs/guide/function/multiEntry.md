---
sidebar_label: 多入口
sidebar_position: 2
---

# 多入口
## 使用 
+ [配置用例](https://github.com/efoxTeam/emp/blob/main/projects/demo2/emp-config.js#L14)
+ [入口](https://github.com/efoxTeam/emp/tree/main/projects/demo2/src/pages) 

## 约定方式 
###  entries?: MultiEntryConfig
```javascript
interface MultiEntryConfig {
  /**
   * 路由 url 如 info/user 或 about 等 映射特殊配置到页面
   * 如: entryCwd 为 src/pages 的话 全路径 src/pages/info/user 配置成 如下配置
   * {
   *  'info/user':{title:"用户管理页面",favicon:"./src/assets/favicon.ico"}
   * }
   */
  [key: string]: {
    title: string
    template?: string
    favicon?: string
    files?: {
      css?: string[]
      js?: string[]
      publicPath?: string
    }
  }
}
```
### entryCwd?: string | boolean
+ 默认多页面入口
+ default src/pages
+ 当为 false 时 将不启动 多入口

## 注意项 
+ entryCwd 入口目录不应存在其他逻辑代码应该要独立于 `src/pages` 外 以为误操作 
+ entryCwd 可以自定义目录 以 `src/`为根目录 当为 `false` 时 取消多入口功能 
