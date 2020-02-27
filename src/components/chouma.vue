<template>
    <div class="chouma">
        <div :style="{backgroundImage:'url('+img[data.jinge]+')'}"></div>
    </div>
</template>
<script>
    import shouma1 from '../assets/img/chouma/1.png'
    import shouma10 from '../assets/img/chouma/10.png'
    import shouma50 from '../assets/img/chouma/50.png'
    import shouma100 from '../assets/img/chouma/100.png'
    import shouma500 from '../assets/img/chouma/500.png'
    export default {
        name: "chouma",
        props:['data'],
        data:()=>{
            return{
                img:{
                    1:shouma1,10:shouma10,50:shouma50,100:shouma100,500:shouma500
                }
            }
        }
    }
</script>

<style scoped>
    .chouma,.chouma>div{
        width: 100%;
        height: 100%;
    }
    .chouma>div{
        border-radius: 50%;
        background-repeat: no-repeat;
        background-size: 100% 100%;
        /*background-image: url("../assets/img/chouma/1.png");*/
    }
</style>