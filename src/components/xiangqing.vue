<template>
    <div class="xiangqing">
        <poptitle title="详情"></poptitle>
        <div class="popcenten">
            <div class="kaijianglishi">
                <van-row class="tableheader">
                    <van-col span="6">开奖时间</van-col>
                    <van-col span="6">开奖号码</van-col>
                    <van-col span="4">结果</van-col>
                    <van-col span="4">大小</van-col>
                    <van-col span="4">单双</van-col>
                </van-row>
                <div class="tablebody" id="tablebody">
                        <kaijianglishi></kaijianglishi>
                </div>
            </div>
            <div class="zoushi">
                <zoushi></zoushi>
            </div>
        </div>
    </div>
</template>

<script>
    import poptitle from "./poptitle";
    import kaijianglishi from "./kaijianglishi";
    import zoushi from "./zoushi";
    // import {Popup } from "vant";
    export default {
        name: "xiangqing",
        components:{
            poptitle,
            kaijianglishi,
            // [Popup.name]:Popup
            zoushi
        },
        data(){
            return {
                tablebody:true
            }
        }
    }
</script>

<style scoped>
  .xiangqing{
      /*height: 100%;*/
      background: #573024;
  }
  .popcenten{
      height: calc(100% - 42px);
  }
  .kaijianglishi{
        width: 100%;
        height: 40%;
        /*border: solid red 1px;*/
  }
  .zoushi{
        height: 60%;
    }
    .tableheader {
        background: #4b2d16;
    }

  .tableheader>.van-col{
      font-size: 1.7vw;
      color: #91663e;
      text-align: center;
      line-height: 2.5vw
  }
    .tablebody{
        background: white;
        height: calc(100% - 2.5vw)
    }
</style>