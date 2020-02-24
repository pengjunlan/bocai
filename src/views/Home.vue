<template>
  <div class="home">
<!--      顶部-->
      <div class="top">
        <div>
            <div class="back"></div>
            <div class="time"></div>
            <div class="list"></div>
        </div>
      </div>
<!--      左边-->
      <div class="left">
          <div>
              <div class="user">
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
                          <div></div>
                      </div>
                  </div>
                  <div>
                      <div>
                          <div></div>
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
  </div>
</template>
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
      background: #42b983;
  }
  .back,.time,.list{
      height: 100%;
      float: left;
  }
  .back,.list{
      width: 40%;
      background: wheat;
  }
  .time{
      width: 20%;
      background: #8e42b5;
  }
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
      border:solid #451466  5px;
      background: #7f1fb9;
  }
  .center>div>div{
      position: absolute;
      top: 2%;
      left: 2%;
      right: 2%;
      bottom: 2%;
      border:solid #8e42b5  5px;
      background: #ad23b9;
  }
  .center>div>div>div{
      position: absolute;
      top: 4%;
      left: 4%;
      right: 4%;
      bottom: 4%;
      border:solid #69baff 5px
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
      background: #8e42b5;
  }
  .center>div,.center>div>div,.center>div>div>div{
      border-radius: 8px;
      border-width: 3px;
      box-shadow: 0px 0px 10px #000000;
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
<script>
    import user from '../components/uer'
    import duzhuo from "../components/duzhuo";
    import chouma from "../components/chouma";
    export default {
      name: 'Home',
        components: {
            user,
            duzhuo,
            chouma
        },
      data:()=>{
          return{
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
              ]
          }
      },

    }
</script>
