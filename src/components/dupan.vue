<template>
    <div class="dupan">
        <div>
            <div>
                <img  class="jinbi" src="../assets/img/xiaojinbi.png" alt="">
            </div>
            <div class="jine">
                <div>5</div>
            </div>
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
    }
    .dupan>div:first-child{
        height: 15%;
        background: #42b983;
    }
    .dupan>div:first-child>div{
        height: 100%;
        float: left;
    }
    .jinbi{
        height: 100%;
    }
    .jine{
        position: relative;
    }
    .jine>div{
        position: relative;
        top: 50%;
        margin-top: -83%;
        text-indent: 5px;
    }
    .dupan>div:last-child{
        height: 85%;
        font-size: 8vh;
        color: #252525;
        text-align: center;
        text-shadow:5px 5px 10px #5a545c;
        background: #b9215e;
    }
</style>