<!--
 * @Author: XueBaBa
 * @Description: 文件描述~
 * @Date: 2020-11-10 16:43:29
 * @LastEditTime: 2020-11-10 17:58:42
 * @LastEditors: Do not edit
 * @FilePath: /vue-todos/src/App.vue
-->
<template>
<div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
</div>
</template>

<script lang="ts">
import HelloWorld from "./components/HelloWorld.vue";

export default {
    name: "app",
    components: {
        HelloWorld
    }
};
</script>

<style>
#app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
