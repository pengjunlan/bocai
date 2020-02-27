<template>
    <div class="kaijiang">
        <van-row>
            <van-col span="3" offset="2"><div class="k">{{k[0]}}</div></van-col>
            <van-col span="3"><div class="kl">+</div></van-col>
            <van-col span="3"><div class="k">{{k[1]}}</div></van-col>
            <van-col span="3"><div class="kl">+</div></van-col>
            <van-col span="3"><div class="k">{{k[2]}}</div></van-col>
            <van-col span="3"><div class="kl">=</div></van-col>
            <van-col span="3"><div class="k">{{(k[0]+k[1]+k[2])%10}}</div></van-col>
        </van-row>
    </div>
</template>

<script>
    import Vue from 'vue';
    import { Col, Row } from 'vant';

    Vue.use(Col);
    Vue.use(Row);
    export default {
        name: "kaijiang",
        data:()=>{
            return {
                k:[4,6,7]
            }
        }
    }
</script>

<style scoped>
    .k,.kl{
        height: 40px;
        width: 40px;
        text-align: center;
        line-height: 40px;
        font-weight: 900;
        font-size: 20px;
        color: white;
    }
    .k{
      background: #69baff;
        border-radius: 50%;
    }
</style>