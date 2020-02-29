<template>
    <div id="zoushi">
        <div class="title">拍形走势</div>
        <div class="a">
             <van-row v-for="(val,key) in data" :key="key">
                 <van-col span="2" v-for="(v,k) in val" :key="k">
                     <div class="b">{{v}}</div>
                 </van-col>
             </van-row>
        </div>
    </div>
</template>

<script>
    export default {
        name: "zoushi",
        data(){
          return{
              data:[
                  ['小','大','小','大','小','大','小','大','小','大','小','大'],
                  ['小','大','小','大','小','大','小','大','小','大','小','大'],
                  ['小','大','小','大','小','大','小','大','小','大','小','大'],
                  ['小','大','小','大','小','大','小','大','小','大','小','大'],
                  ['小','大','小','大','小','大','小','大','小','大','小','大'],
                  ['小','大','小','大','小','大','小','大','小','大','小','大'],
                  ['小','大','小','大','小','大','小','大','小','大','小','大'],

              ]
          }
        },
    }
</script>

<style scoped>
.title{
    font-weight: 900;
    text-align: center;
    font-size: 1.3vw;
    color: #c7a031;
}
/*.a{*/
/*    overflow: scroll;*/
/*    border: solid red 1px;*/
/*}*/
.van-col{
    padding: 1%;
}
.b{
    color: white;
    font-size: 1.5vw;
    text-align: center;
}
.van-row>.van-col:nth-child(even)>.b{
    background: #85252c;
}
.van-row>.van-col:nth-child(odd)>.b{
    background: #647eb9;
}

</style>