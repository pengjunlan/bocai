<template>
    <div>
        <poptitle title="抢庄"></poptitle>
        <div class="popcenten">
            <div>
                <van-button round type="info" size="small" @click="qiangzhuangfun(0)">不抢庄</van-button>
                <van-button round type="info" size="small" v-for="(val,key) in qiangzhuang" :key="key" @click="qiangzhuangfun(val)">{{val}}</van-button>
            </div>
        </div>
    </div>
</template>

<script>
    import Poptitle from "./poptitle";
    import {Button} from 'vant'
    import store from "../store";
    export default {
        store,
        name: "qiangzhuang",
        data:()=>{
          return {
              qiangzhuang:[100,1000,2000,5000,10000]
          }
        },
        components: {
            Poptitle,
            [Button.name]:Button
        },
        methods:{
            qiangzhuangfun:function(jine){
                console.log(jine)
                this.$parent.$parent.popup.qiangzhuang=false
                this.$parent.$parent.start();
            }
        }
    }
</script>

<style scoped>
.popcenten>div{
    text-align: center;
}
.popcenten>div>.van-button{
    margin: 10px 10px;
    background: #ff041c;
    border: solid #FF041C 1px;
}
</style>