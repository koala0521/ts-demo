<!--
 * @Author: XueBaBa
 * @Description: 文件描述~
 * @Date: 2020-11-10 17:02:17
 * @LastEditTime: 2020-11-10 17:50:48
 * @LastEditors: Do not edit
 * @FilePath: /vue-todos/vue项目配置ts教程.md
-->
# vue项目配置ts教程



vue项目配置ts的两种方式：

## 1. 新项目配置 ts

新项目比较简单，使用 vue-cli 创建项目的时候会有选项，我们使用方向键跳转到 typescript ，按空格键确认。 然后一直下一步... 。就可以了。


## 2. 老项目配置 ts

1.首先进入我们的 vue。

2.安装依赖


    ```
        npm install --save-dev typescript
        npm install --save-dev @vue/cli-plugin-typescript

    ```
3.增加typescript配置文件

根目录新建文件 `tsconfig.json` 。详细配置可看官方文档（https://www.tslang.cn/docs/handbook/tsconfig-json.html）

简单的配置如下：

```json

{
    "compilerOptions": {
      "target": "esnext",
      "module": "esnext",
      "strict": true,
      "importHelpers": true,
      "moduleResolution": "node",
      "experimentalDecorators": true,
      "esModuleInterop": true,
      "allowSyntheticDefaultImports": true,
      "sourceMap": true,
      "baseUrl": ".",
      "allowJs": false,
      "noEmit": true,
      "types": [
        "webpack-env"
      ],
      "paths": {
        "@/*": [
          "src/*"
        ]
      },
      "lib": [
        "esnext",
        "dom",
        "dom.iterable",
        "scripthost"
      ]
    },
    "exclude": [
      "node_modules"
    ]
}

```

4. 新增 shims-vue.d.ts 文件。让 ts 识别 *.vue 文件，文件内容如下：

```js
declare module '*.vue' {
  import Vue from 'vue'
  export default Vue
}

```

5. 修改入口文件后缀 

`src/main.js => src/main.ts`


6.改造 .vue 文件。让.vue文件中使用 ts 实例


```js

// 加上 lang=ts 让webpack识别此段代码为 typescript
<script lang="ts">
  import Vue from 'vue'
  export default Vue.extend({
    // ...
  })
</script>

```

7. 重新启动项目即可



## 一些好用的插件

`vue-class-component`（文档 https://class-component.vuejs.org/ ）

强化 Vue 组件，使用 TypeScript装饰器 增强 Vue 组件，使得组件更加扁平化

