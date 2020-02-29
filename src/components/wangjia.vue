<template>
    <div>
        <poptitle title="玩家"></poptitle>
        <div class="popcenten">
            <wanjiadange v-for="(val,key) in wangjialist" :key="key" :data="val"></wanjiadange>
        </div>
    </div>
</template>

<script>
    import poptitle from "./poptitle";
    import  wanjiadange from "./wanjiadange"
    export default {
        name: "wangjia",
        components:{
            poptitle,
            wanjiadange
        },
        data(){
            return {
                wangjialist:[
                    {touxaing:'http://t8.baidu.com/it/u=1484500186,1503043093&fm=79&app=86&f=JPEG?w=1280&h=853',name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                    {touxaing:0,name:'asdfasdf',qian:45455},
                ]
            }
        }
    }
</script>

<style scoped>

</style>