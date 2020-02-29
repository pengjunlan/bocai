<template>
    <div class="kaijianglishiinfo">
        <van-row v-for="(val,key) in data" :key="key">
            <van-col span="6">{{val.time}}</van-col>
            <van-col span="6">{{val.num}}</van-col>
            <van-col span="4">{{val.jieguo}}</van-col>
            <van-col span="4">{{val.daxiao}}</van-col>
            <van-col span="4">{{val.danshuang}}</van-col>
        </van-row>
    </div>
</template>

<script>
    export default {
        name: "kaijianglishi",
        data(){
            return {
                data:[
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                    {time:'2018/1/1 12:45',num:'456789',jieguo:'4',daxiao:'大',danshuang:'双'},
                ]
            }
        }
    }
</script>

<style scoped>
.kaijianglishiinfo{
    overflow: scroll;
    height: 15vh;
}
.kaijianglishiinfo>.van-row>.van-col{
    text-align: center;
    color:  #573024;
    padding: 1%;
    font-size: 1.3vw;
}
</style>