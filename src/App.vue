<template>
    <img alt="Vue logo" src="./assets/logo.png">
    <h2>欢迎光临红浪漫洗浴中心</h2>
    <div>请选择一位美女为您服务</div>
    <div>
        <button
            v-for="(item,index) in girls"
            v-bind:key='index'
            @click="selectGirlFunc(index)"
            >
            {{index+1}}:{{item}}
        </button>
    </div>
    <div>你选择了[{{ selectGirl }}]为你服务</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
    name: 'App',
    setup() {
        const girls = ref(['长公主', '扶香花魁', '勾栏听曲儿']);
        const selectGirl = ref('');
        const selectGirlFunc = (index: number) => {
        selectGirl.value = girls.value[index];
        };
        return{
            girls,
            selectGirl,
            selectGirlFunc
        }
    },
})
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
