<template>
    <div>
        <h2>欢迎光临红浪漫洗浴中心</h2>
        <div>随机抽取一位美女为您服务</div>
        <div v-if="loading">loading...</div>
        <img v-if="loaded" :src="result.imgUrl" alt="">
    </div>
</template>

<script lang="ts">
import useUrlAxios from './hooks/uesURLAxios'

export default {
    name: 'App',
    setup() {
        const {result, loading, loaded} = useUrlAxios('https://apiblog.jspang.com/default/getGirl')

        return {result, loading, loaded}
    },
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
