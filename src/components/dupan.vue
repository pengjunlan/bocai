<template>
    <div class="dupan">
        <div>
            <div>
                <img  class="jinbi" src="../assets/img/xiaojinbi.png" alt="">
                <span>asdfasdf</span>
            </div>
<!--            <div>-->
<!--                <img  class="jinbi" src="../assets/img/xiaojinbi.png" alt="">-->
<!--            </div>-->
<!--            <div class="jine">-->
<!--                <div>5</div>-->
<!--            </div>-->
        </div>
        <div>
            大
        </div>
    </div>
</template>

<script>
    export default {
        name: "dupan"
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
        background: #42b983;
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
        color: white;
        line-height: 20vh;
        text-align: center;
        text-shadow:5px 5px 10px #5a545c;
        background: #b9215e;
    }
</style>