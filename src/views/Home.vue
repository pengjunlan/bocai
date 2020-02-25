<template>
  <div class="home">
<!--      弹框-->
      <van-popup closeable close-icon="close"  :style="{ height: '50%',width:'50%' }" v-model="popup.shuoming">内容</van-popup>
      <van-popup closeable close-icon="close"  :style="{ height: '50%',width:'50%' }" v-model="popup.wangjia">wangjia</van-popup>
      <van-popup closeable close-icon="close"  :style="{ height: '50%',width:'50%' }" v-model="popup.xiangqing">xiangqing</van-popup>
<!--      顶部-->
      <div class="top">
        <div>
            <div class="back">
                <div class="menulist">
                    <div :style="{backgroundImage: 'url('+img.fanhuei+')'}"></div>
                </div>
            </div>
            <div class="time">
               50请下注
            </div>
            <div class="list">
                <div class="menulist" @click="shuoming()">
                    <div :style="{backgroundImage: 'url('+img.shuoming+')'}"></div>
                </div>
                <div class="menulist" @click="wangjia()">
                    <div :style="{backgroundImage: 'url('+img.wangjia+')'}"></div>
                </div>
                <div class="menulist" @click="xiangqing()">
                    <div :style="{backgroundImage: 'url('+img.xiangqing+')'}" ></div>
                </div>
            </div>
        </div>
      </div>
<!--      左边-->
      <div class="left">
          <div>
              <div class="user" >
                  <user class="touxiang" v-for="(val,key) in touxiang.left" :key="key"></user>
              </div>
              <div class="my-user">
                  <user class="mytou"></user>
              </div>
          </div>
      </div>
<!--      右边-->
      <div class="right">
          <div>
              <div class="user">
                  <user class="touxiang" v-for="(val,key) in touxiang.left" :key="key"></user>
              </div>
              <div class="start-buttom">
                  <div>
                      <div>
                          <div>玩家</div>
                      </div>
                  </div>
                  <div>
                      <div>
                          <div>开始</div>
                      </div>
                  </div>
              </div>
          </div>
      </div>
<!--       底部-->
      <div class="bottom">
           <div class="fama" :style="{width:100/fama.length+'%'}" v-for="(val,key) in fama" :key="key">
               <div>
                   <div>
                        <chouma></chouma>
                   </div>
               </div>
           </div>
      </div>
<!--      中部-->
      <div class="center">
          <div>
              <div>
                  <div class="du-zhuo">
                      <duzhuo></duzhuo>
                  </div>
              </div>
          </div>
      </div>
<!--      <van-button type="info">信息按钮</van-button>-->
<!--      <van-button type="warning">警告按钮</van-button>-->
<!--      <van-button type="danger">危险按钮</van-button>-->
  </div>
</template>
<script>
    import user from '../components/uer'
    import duzhuo from "../components/duzhuo";
    import chouma from "../components/chouma";
    import wangjia from '../assets/img/wanjiananliu.png'
    import shuoming from '../assets/img/shuominganliu.png'
    import xiangqing from '../assets/img/xiangqinganliu.png'
    import fanhuei from '../assets/img/fanhueianliu.png'
    import { Button,Popup } from "vant"
    export default {
        name: 'Home',
        components: {
            user,
            duzhuo,
            chouma,
            [Button.name]:Button,
            [Popup.name]:Popup,
        },
        data:()=>{
            return{
                img:{
                    wangjia,shuoming,xiangqing,fanhuei
                },
                touxiang:{
                    left:[
                        {},
                        {},
                        {}
                    ],
                    right:[
                        {},
                        {},
                        {}
                    ],
                    mytou:{

                    }
                },
                fama:[
                    {},
                    {},
                    {},
                    {},
                    {},
                ],
                popup:{
                    shuoming:false,
                    wangjia:false,
                    xiangqing:false,
                }
            }
        },
        methods: {
            shuoming:function(){
                console.log(55)
                this.popup.shuoming = true
            },
            wangjia:function(){
                console.log(55)
                this.popup.wangjia = true
            },
            xiangqing:function(){
                console.log(55)
                this.popup.xiangqing = true
            },

        }
    }
</script>

<style scoped>
  .home{
      width: 100%;
      height: 100%;
      min-width: 500px;
      min-height: 300px;
      background-image: url("../assets/img/beijing.jpg");
      background-size: 100% 100%;
      background-repeat: no-repeat;
  }
  .home>div{
      position: absolute;
  }
  .top{
      top: 0px;
      left: 0px;
      width: 100%;
      height: 15%;
  }
  .top>div{
      width: 100%;
      height: 90%;
      /*background: #42b983;*/
  }
  .back,.time,.list{
      height: 100%;
      float: left;
  }
  .back,.list{
      width: 40%;
      /*background: wheat;*/
  }

  .time{
      /*position: relative;*/
      width: 20%;
      color: white;
      /*background: #8e42b5;*/
      text-align: center;
      font-size: 5vh;
  }
  /*.time>div{*/
  /*    position: absolute;*/
  /*    top: 50%;*/
  /*    margin-top: -50%;*/
  /*    display: inline-block;*/
  /*    background: #4f67b5;*/
  /*}*/
  .right,.left{
      width: 15%;
      top: 15%;
      height: 85%;
  }
  .right>div,.left>div{
      width: 90%;
      margin: 0 auto;
      bottom: 15%;
      height: 100%;
  }
   .right{
       right: 0px;
   }
   .left{
        left:0px
   }
   .user{
       height: 75%;
       width: 100%;;
   }
   .back>.menulist{
       float: left;
       margin-left:5% ;
   }
   .list>.menulist{
       float: right;
       margin-right:5%;
   }
   .menulist{

        position: relative;

        width: 15%;
        height: 100%;
   }
  .menulist>div{
      position: absolute;
      top: 50%;
      margin-top: -50%;
      width: 100%;
      padding-bottom: 100%;
      background-size:100% 100%;
      background-position: center center;
  }
   .touxiang{
       width: 100%;
       height: 33.33%;
       max-width: 150px;
   }
  .left .touxiang{
      float: right;
  }
  .right .touxiang{
      float: left;
  }
   .mytou{
       width: 100%;
       max-width: 150px;
       height: 100%;
       float: right;
       /*background: #4b2d16;*/
   }
   .my-user,.start-buttom{
       width: 100%;
       height: 25%;
   }
   .start-buttom>div{
       position: relative;
       width: 50%;
       height: 100%;
       float: left;
   }
  .start-buttom>div>div{
      position: absolute;
      bottom: 10%;
      width: 100%;
      padding-bottom: 100%;
  }
  .start-buttom>div>div>div{
      position: absolute;
      top: 10%;
      bottom: 10%;
      left: 10%;
      right: 10%;
      background: #a26c16;
  }
  .bottom{
      left: 15%;
      right: 15%;
      bottom: 0;
      min-height: 10px;
      /*background: #1f4689;*/
  }
  .center{
      top: 15%;
      left: 15%;
      right: 15%;
      bottom: 10%;
  }
/*    du-zhuo*/
  .center>div{
      position: absolute;
      top: 1%;
      left: 1%;
      right: 1%;
      bottom: 1%;
      /*border:solid #451466  5px;*/
      background-image: url("../assets/img/duzuo.png");
      background-size: 106% 113%;
      background-position: 53% 50%;
  }
  .center>div>div{
      position: absolute;
      top: 2%;
      left: 2%;
      right: 2%;
      bottom: 2%;
      /*border:solid #8e42b5  5px;*/
      /*background: #ad23b9;*/
  }
  .center>div>div>div{
      position: absolute;
      top: 4%;
      left: 4%;
      right: 4%;
      bottom: 4%;
      /*border:solid #69baff 5px*/
  }
  .du-zhuo{
      position: absolute;
      top: 5%;
      left: 5%;
      right: 5%;
      bottom: 5%;
  }
  .du-zhuo>.duzuo{
      width: 100%;
      height: 100%;
      /*background: #8e42b5;*/
  }
  .center>div,.center>div>div,.center>div>div>div{
      border-radius: 8px;
      border-width: 3px;
      /*box-shadow: 0px 0px 10px #000000;*/
  }
  .fama{
      position: relative;
      z-index: 100;
      max-width: 100px;
      float: right;
  }
  .fama>div{
      position: relative;
      padding-bottom: 100%;
      margin-bottom: 5%;
  }
  .fama>div>div{
      position: absolute;
      top: 5%;
      left: 5%;
      right: 5%;
      bottom: 5%;
      border-radius: 50%;
      /*background: #a26c16;*/
  }
  @media screen and (max-width: 700px) {
      .center>div,.center>div>div,.center>div>div>div{
          border-width: 2px;
          border-radius: 5px;
      }
      .fama{
          max-width: 70px;
      }
  }

</style>
