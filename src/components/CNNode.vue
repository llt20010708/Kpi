<template>
    <div id="cnnodeWrapper">
        <div id="cnnodeTitle">
            <span>cnnode论坛</span>
        </div>
        <hr>
        <div id="cnnodeContent">
            <li v-for="(value,index2) in this.topicsArr" :key="index2">
                <span>
                    <img id="avatar" :src="value.author.avatar_url" alt="">
                </span>
                <span>
                    {{value.title}}
                </span>
            </li>
        </div>
    </div>
</template>

<script>
import Axios from "axios"

export default {
    data(){
        return{
            topicsArr:[]
        }
    },
    beforeCreate() {
        // console.log("this is vue before")
    },
    created(){
        let that = this
        // 生命周期函数
        // console.log("this vue is running")
        Axios.get('https://cnodejs.org/api/v1/topics').then(function(response){
            // console.log(response.data)
            if(response.data.success){
                that.topicsArr =response.data.data;
            }
        })
    }
}
</script>

<style>
    #avatar{
        width: 20px;
        height: 20px;
    }
</style>