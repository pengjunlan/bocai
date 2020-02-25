<template>
    <div class="duzuo">
        <div v-for="(val,key) in duzhuo" :key="key" :style="{height:(100/duzhuo.length)+'%'}">
            <div v-for="(v,k) in val" :key="k" :style="{width:(100/val.length)+'%'}">
                <div>
                    <dupan></dupan>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import dupan from "./dupan";
    export default {
        name: "duzhuo",
        components:{
            dupan
        },
        data:()=>{
            return{
                duzhuo:[
                    [
                        []
                    ],
                    [
                        [],
                        []
                    ]
                ]
            }
        }
    }
</script>

<style scoped>
.duzuo>div{
    /*background: #648844;*/
}
.duzuo>div>div{
    position: relative;
    height: 100%;
    float: left;
}
.duzuo>div>div>div{
    position: absolute;
    top: 2px;
    left: 2px;
    right: 2px;
    bottom: 2px;
    /*background: #16418a;*/
}
</style>