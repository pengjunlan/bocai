<template>
    <div class="wanjiadange">
        <div>
            <div class="tou">
                <img  src="../assets/img/touxiang/tou.png">
            </div>
            <div class="name">
                {{data.name}}
            </div>
            <div class="j">
                <div class="jinbi">

                </div>
                <div class="jine">
                    {{data.qian}}
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: "wanjiadange",
        props:['data'],
    }
</script>
<style scoped>
    .wanjiadange{
        width: 50%;
        min-height: 2px;
        float: left;
    }
    .wanjiadange>div{
        background: #fff5b5;
        margin: 1%;
        box-shadow: 0px 0px 1px black;
        border-radius: 2px;
        padding: 1%;
        overflow: hidden;
    }
    .wanjiadange>div>div:first-child{
        width: 30%;
        text-align: center;
    }
    .wanjiadange>div>div:first-child~div{
        margin-left: 20%;
        margin-right: 10%;
        width: 40%;
        /*background: greenyellow;*/
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    .wanjiadange>div>div:last-child{
        margin-top: 2%;
    }
    .wanjiadange>div>div{
        float: left;
    }
    .tou>img{
        width: 90%;
        border-radius: 50%;
        border:solid #ffdd84 2px;
        box-shadow: 0px 0px 1px black;
    }
    .j{
        background: rgba(0,0,0,0.3);
        border-radius: 1000px;
    }
    .jinbi,.jine{

        float: left;
    }
    .jinbi{
        padding-bottom:20% ;
        background-image: url("../assets/img/xiaojinbi.png");
        width: 20%;
    }
    .jine{
        /*background: #b93f79;*/
        width: 79%;
        line-height: 1.9vw;
        font-size: 1vw;
        text-indent: 5%;
        color: #f3de59;
    }
    .name{
        line-height: 1.9vw;
        color: #c7a031;
        font-weight: 900;
        font-size: 1.5vw;
    }
    @media screen  and (max-width: 700px){
        .wanjiadange{
            width: 100%;
            min-height: 2px;
            float: left;
            border: solid red 1px;
        }
    }
</style>