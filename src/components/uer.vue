<template>
    <div class="user">
        <van-popup :close-on-click-overlay="false" :style="{ height: '50%',width:'50%' }" v-model="popup.userinfo" get-container="body"><popuserinfo></popuserinfo></van-popup>
<!--        <div class="u"  @click="userinfo()">-->
        <div class="u">
            <div>
                <div class="touxiang">
<!--                    <img src="../assets/img/touxiang/tou1.png" alt="">-->
                    <img :src="tou[data.touxiang]" alt="">
                </div>
            </div>
            <div class="username">
                <div>{{data.name}}</div>
            </div>
            <div class="qian">
                <div>{{data.jie}}</div>
            </div>
            <div v-show="data.kaitype" class="jiazhu" :class="{jiazhuleft:jiazhufangmiang=='left',jiazhuright:jiazhufangmiang=='right'}"><span>{{data.kaijing}}</span></div>
        </div>
    </div>
</template>

<script>
    //  {name:'asdfasd',jie:'20114',kaijing:'+458',kaitype:false,touxiang:1},
    import popuserinfo from '../components/userinfo'
    import tou1 from '../assets/img/touxiang/tou1.png'
    import tou2 from '../assets/img/touxiang/tou2.png'
    import tou3 from '../assets/img/touxiang/tou3.png'
    import tou4 from '../assets/img/touxiang/tou4.png'
    import tou5 from '../assets/img/touxiang/tou5.png'
    import { Popup } from "vant"
    export default {
        name: "uer",
        components:{
            popuserinfo,
            [Popup.name]:Popup
        },
        data:()=>{
          return{
              popup:{
                  userinfo:false,
              },
              tou:[tou1,tou2,tou3,tou4,tou5]
          }
        },
        props:['jiazhu','jiazhufangmiang','data'],
        methods:{
            userinfo:function(){
                console.log(55)
                this.popup.userinfo = true
            }
        }
    }
</script>
<style scoped>
    .user{
        /*height:100%;*/
        /*width: 100%;*/
    }
    .u{
        position: relative;
        height:100%;
        width: 100%;
        /*background: #5c728a;*/
    }
    .jiazhuleft{
        right: -40%;
    }
    .jiazhuright{
        left: -40%;
    }
    .jiazhu{
        position: absolute;
        top: 0px;
        font-size: 5vh;
        z-index: 1000;
        /*border:solid red 1px;*/
        line-height: 21vh;
        height: 100%;
        font-weight: bold;
    }
   .u>div:first-child{
       height: 50%;
       /*background: #8e42b5;*/
   }
    .touxiang{
        text-align: center;
        height: 100%;
    }
    .touxiang>img{
        border-radius: 50%;
        height: 100%;
    }
    .username,.qian{
        text-align: center;
    }
    .username>div,.qian>div{
        margin: 1% auto;
        width: 80%;
        text-align: center;
        padding: 1% 5%;
        background: rgba(0,0,0,0.5);
        border-radius: 100px;
        color: white;
        font-size: 3vh;
    }
</style>