<template>
    <img alt="Vue logo" src="./assets/logo.png">
    <h2>欢迎光临红浪漫洗浴中心</h2>
    <div>请选择一位美女为您服务</div>
    <div>
        <button
            v-for="(item,index) in girls"
            :key='index'
            @click="selectGirlFunc(index)"
            >
            {{index+1}}:{{item}}
        </button>
    </div>
    <div>你选择了【{{ selectGirl }}】为你服务</div>
</template>

<script lang="ts">
import { toRefs, ref, reactive } from 'vue';
interface DataProps{
    girls: string[];
    selectGirl: string;
    selectGirlFunc: (index: number) => void;
}

export default {
    name: 'App',
    setup() {

        const data:DataProps = reactive({
            girls: ['小罗', '罗姨', '罗老师'],
            selectGirl: '',
            selectGirlFunc: (index: number) => {
                data.selectGirl = data.girls[index];
            }
        })

        const refData = toRefs(data)

        // const girls = ref();
        // const selectGirl = ref('');
        // const selectGirlFunc = (index: number) => {
        //     selectGirl.value = girls.value[index];
        // };

        return{
            ...refData
        }
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
