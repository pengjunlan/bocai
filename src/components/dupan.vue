<template>
    <div class="dupan">
        <div>
            <div>
                <img  class="jinbi" src="../assets/img/xiaojinbi.png" alt="">
                <span>{{data.xiazujine}}</span>
            </div>
<!--            <div>-->
<!--                <img  class="jinbi" src="../assets/img/xiaojinbi.png" alt="">-->
<!--            </div>-->
<!--            <div class="jine">-->
<!--                <div>5</div>-->
<!--            </div>-->
        </div>
        <div class="choumazuo" @click="xiazhu()">
            {{data.zi}}
            <div class="chouma" :style="{top:v.top+'%',left:v.left+'%'}" v-for="(v,k) in shouma" :key="k">
                <chouma :data="{jinge:v.jinge}"></chouma>
            </div>
        </div>
    </div>
</template>

<script>
    import chouma from "./chouma";
    // import store from '../store'
    export default {
        name: "dupan",
        components:{
            chouma
        },
        props:['data'],
        data(){
            return {
                shouma:[
                    {jinge:50,top:'10',left:'6'}
                ]
            }
        },
        watch:{
            'shouma':function(val){
                this.data.xiazujine=0
                for (var i = 0 ;i < val.length;i++){
                    // console.log(val[i].jinge)
                    this.data.xiazujine +=val[i].jinge
                }
            }
        },
        methods:{
            xiazhu(){
                if(this.$parent.$parent.xuanzejine <=0){
                    return false;
                }
                // console.log(this.$store.state.jine)
                console.log(this.$parent.$parent.xuanzejine)
                var top=Math.round(Math.random()*80)+10;
                var left = Math.round(Math.random()*80)+10;
                this.shouma.push({
                    jinge:this.$parent.$parent.xuanzejine,
                    top:top,
                    left:left
                })
            }
        }
    }
</script>

<style scoped>
    .dupan{
        width: 100%;
        height: 100%;
        border-radius: 5px;
        overflow: hidden;
    }
    .dupan>div:first-child{
        position: relative;
        height: 15%;
        /*background: #42b983;*/
        background: linear-gradient(to right, #2cb15b, #f3dda8);
    }
    .dupan>div:first-child>div{
        position: absolute;
        top: 15%;
        bottom: 15%;
        left: 0;
        right: 0;
        padding-left: 2%;
        /*background: #8e42b5;*/
        /*line-height: 4vh;*/
    }
    .dupan>div:first-child>div>span{
        position: relative;
        top: -20%;
        left: 2%;
        height: 100%;
        width: 80%;
        display: inline-block;
        /*background: #6b9cb9;*/
        /*line-height: 4vh;*/
        font-size: 3vh;
        color: #201d22;
    }
    .jinbi{
        height: 100%;
    }
    /*.jine{*/
    /*    position: relative;*/
    /*}*/
    .jine>div{
        position: relative;
        top: 50%;
        margin-top: -83%;
        text-indent: 5px;
    }
    .dupan>div:last-child{
        height: 85%;
        font-size: 8vh;
        color: #c2a877;
        line-height: 20vh;
        text-align: center;
        /*text-shadow:5px 5px 10px #5a545c;*/
        background: #f3dda8;
    }
    .choumazuo{
        position: relative;
    }
    .chouma{
        position: absolute;
        top: 0;
        left: 0;
        height: 25px;
        width: 25px;
        animation: myfirst 1s;
        /*-moz-animation: myfirst 1s;	!* Firefox *!*/
        /*-webkit-animation: myfirst 1s;	!* Safari 和 Chrome *!*/
        /*-o-animation: myfirst 1s;	!* Opera *!*/
    }
    @keyframes myfirst
    {
        from {
            width: 50px;
            height: 50px;
        }
        to {
            height: 25px;
            width: 25px;
        }
    }

    /*@-moz-keyframes myfirst !* Firefox *!*/
    /*{*/
    /*    from {background: red;}*/
    /*    to {background: yellow;}*/
    /*}*/

    /*@-webkit-keyframes myfirst !* Safari 和 Chrome *!*/
    /*{*/
    /*    from {background: red;}*/
    /*    to {background: yellow;}*/
    /*}*/

    /*@-o-keyframes myfirst !* Opera *!*/
    /*{*/
    /*    from {background: red;}*/
    /*    to {background: yellow;}*/
    /*}*/
</style>