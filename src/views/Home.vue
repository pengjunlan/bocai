<template>
  <div class="home">
<!--      弹框-->
      <van-popup :close-on-click-overlay="false" :style="{ height: '50%',width:'50%' }" v-model="popup.shuoming"><popshuoming></popshuoming></van-popup>
      <van-popup :close-on-click-overlay="false" :style="{ height: '50%',width:'50%' }" v-model="popup.wangjia"><popwangjia></popwangjia></van-popup>
      <van-popup :close-on-click-overlay="false" :style="{ height: '50%',width:'50%' }" v-model="popup.xiangqing"><popxiangqing></popxiangqing></van-popup>
      <van-popup :close-on-click-overlay="false" :style="{ height: '50%',width:'50%',background:'rgba(0,0,0,0)'}" v-model="popup.qiangzhuang"><qiangzhuang></qiangzhuang></van-popup>
      <van-popup :close-on-click-overlay="false" :style="{ height: '50%',width:'50%',background:'rgba(0,0,0,0)'}" v-model="popup.kaishixiazhu"><kaishixiazhu></kaishixiazhu></van-popup>
      <van-popup :close-on-click-overlay="false" :style="{ height: '50%',width:'50%',background:'rgba(0,0,0,0)'}" v-model="popup.tingzhixiazhu"><tingzhixiazhu></tingzhixiazhu></van-popup>
      <van-popup :close-on-click-overlay="false" :style="{ height: '50%',width:'50%',background:'rgba(0,0,0,0)'}" v-model="popup.kaijiang"><kaijiang></kaijiang></van-popup>
<!--      顶部-->
      <div class="top">
        <div>
            <div class="back">
<!--                <div class="menulist">-->
<!--                    <div :style="{backgroundImage: 'url('+img.fanhuei+')'}"></div>-->
<!--                </div>-->
            </div>
            <div class="time" v-show="isdiplaytime">
               {{time}}请下注
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
                  <user class="touxiang" v-for="(val,key) in touxiang.left" :key="key" jiazhufangmiang="left" :data="val"></user>
              </div>
              <div class="my-user">
                  <user class="mytou" jiazhufangmiang="left" :data="touxiang.mytou"></user>
              </div>
          </div>
      </div>
<!--      右边-->
      <div class="right">
          <div>
              <div class="user">
                  <user class="touxiang" v-for="(val,key) in touxiang.left" :key="key" jiazhufangmiang="right" :data="val"></user>
              </div>
              <div class="start-buttom">
<!--                  <div>-->
<!--                      <div>-->
<!--                          <div>-->
<!--&lt;!&ndash;                              玩家&ndash;&gt;-->
<!--                          </div>-->
<!--                      </div>-->
<!--                  </div>-->
<!--                  <div>-->
<!--                      <div>-->
<!--                          <div>开始</div>-->
<!--                      </div>-->
<!--                  </div>-->
              </div>
          </div>
      </div>
<!--       底部-->
      <div class="bottom">
           <div class="fama" :style="{width:100/fama.length+'%'}" v-for="(val,key) in fama" :key="key">
               <div>
                   <div>
                        <chouma :data="val"></chouma>
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
  </div>
</template>
<script>
    import popxiangqing from '../components/xiangqing';
    import popwangjia from '../components/wangjia';
    import popshuoming from '../components/shuoming';
    import user from '../components/uer'
    import duzhuo from "../components/duzhuo";
    import chouma from "../components/chouma";
    import wangjia from '../assets/img/wanjiananliu.png';
    import shuoming from '../assets/img/shuominganliu.png';
    import xiangqing from '../assets/img/xiangqinganliu.png';
    import fanhuei from '../assets/img/fanhueianliu.png';
    import qiangzhuang from '../components/qiangzhuang';
    import kaishixiazhu from '../components/kaishixiazhu';
    import tingzhixiazhu from '../components/tingzhixiazhu';
    import kaijiang from '../components/kaijiang';
    import { Button,Popup } from "vant";
    import store from '../store'
    export default {
        store,
        name: 'Home',
        components: {
            kaishixiazhu,
            tingzhixiazhu,
            popxiangqing,
            popwangjia,
            popshuoming,
            kaijiang,
            user,
            duzhuo,
            chouma,
            qiangzhuang,
            [Button.name]:Button,
            [Popup.name]:Popup,
        },
        watch:{
          'touxiang.kaitype':function(val){
              // console.log(odlval)
              console.log(val)
              for(var i in this.touxiang.right){
                  this.touxiang.right[i]['kaitype']=val
              }
              for(var k in this.touxiang.left){
                  this.touxiang.left[k]['kaitype']=val
              }
          }
        },
        data:()=>{
            return{
                img:{
                    wangjia,shuoming,xiangqing,fanhuei
                },
                touxiang:{
                    kaitype:false,
                    left:[
                        {name:'asdfasd',jie:'20114',kaijing:'+458',kaitype:false,touxiang:1},
                        {name:'asdfasd',jie:'20114',kaijing:'+458',kaitype:false,touxiang:1},
                        {name:'asdfasd',jie:'20114',kaijing:'+458',kaitype:false,touxiang:1},
                    ],
                    right:[
                        {name:'asdfasd',jie:'20114',kaijing:'+458',kaitype:false,touxiang:1},
                        {name:'asdfasd',jie:'20114',kaijing:'+458',kaitype:false,touxiang:1},
                        {name:'asdfasd',jie:'20114',kaijing:'+458',kaitype:false,touxiang:1},
                    ],
                    mytou:{name:'asdfasd',jie:'20114',kaijing:'+458',kaitype:false,touxiang:1}
                },
                fama:[
                    {jinge:1},
                    {jinge:10},
                    {jinge:50},
                    {jinge:100},
                    {jinge:500},
                ],
                popup:{
                    shuoming:false,
                    wangjia:false,
                    xiangqing:false,
                    qiangzhuang:true,
                    kaishixiazhu:false,
                    tingzhixiazhu:false,
                    kaijiang:false
                },
                //倒计时时间
                timedata:5,
                time:0,
                // 动画时间
                atime:3000,
                isdiplaytime:false
            }
        },
        methods: {
            jieshukaijiang:function(){
                var e = this;
                setTimeout(function(){
                    e.touxiang.kaitype=false;
                    e.popup.qiangzhuang=true;
                },this.atime)
            },
            kaijiang:function(){
                this.popup.kaijiang=true;
                var e = this;
                setTimeout(function(){
                    e.popup.kaijiang=false;
                    // e.kaijiang();
                    e.touxiang.kaitype=true;
                    e.jieshukaijiang();
                },this.atime)
            },
            tingzhixiazhu:function(){
                this.popup.tingzhixiazhu=true;
                var e = this;
                setTimeout(function(){
                    e.popup.tingzhixiazhu=false;
                    e.kaijiang();
                },this.atime)
            },
            start:function(){
                var e = this;
                e.popup.kaishixiazhu=true
                setTimeout(function(){
                    e.popup.kaishixiazhu=false
                    //倒计时的时间
                    e.time=e.timedata
                    e.daojishi()

                },this.atime)
            },
            daojishi:function(){
                this.isdiplaytime = true;
                var e = this;
                setTimeout(function(){
                    if(e.time>1){
                        e.time--
                        e.daojishi()
                    }else{
                        e.isdiplaytime=false;
                        e.tingzhixiazhu();
                    }
                },1000)
            },
            shuoming:function(){
                this.popup.shuoming = true
            },
            wangjia:function(){
                this.popup.wangjia = true
            },
            xiangqing:function(){
                this.popup.xiangqing = true
            }
        },
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
  .back,.time{
      height: 100%;
      float: left;
  }
  .list{
      height: 100%;
      float: right;
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
       /*width: 50%;*/
       width: 100%;
       height: 100%;
       float: left;
   }
  .start-buttom>div>div{
      position: absolute;
      bottom: 10%;
      width: 100%;
      /*padding-bottom: 100%;*/
      padding-bottom: 50%;
  }
  .start-buttom>div>div>div{
      position: absolute;
      top: 10%;
      bottom: 10%;
      left: 10%;
      right: 10%;
      /*background: #a26c16;*/
      background-image: url("../assets/img/xutou.png");
      background-size: 100% 100%;
      background-position: center center;
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
      border:solid #f3dda8 5px;
      box-shadow: 0px 0px 4px black;
      background: #593b22;
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
