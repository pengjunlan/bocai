<template>
    <div class="poptitle">
        <div>{{title}}</div>
    </div>
</template>

<script>
    export default {
        name: "poptitle",
        props:['title']
    }
</script>

<style scoped>
    .poptitle{
        height: 30px;
        background: #000000;
        text-align: center;
    }
    .poptitle>div{
        display: inline-block;
        height: 80%;
        /*border: #8e42b5 solid 1px;*/
        padding: 0 5%;
        color: white;
        background: #b90612;
        border-radius: 0 0px 5px 5px;
    }
</style>