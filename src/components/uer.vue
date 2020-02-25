<template>
    <div class="user">
        <div class="u">
            <div>
                <div class="touxiang">
                    <img src="../assets/img/touxiang/tou1.png" alt="">
                </div>
            </div>
            <div class="username">
                <div>asdfas</div>
            </div>
            <div class="qian">
                <div>asdfasd</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "uer",
        components:{

        }
    }
</script>

<style scoped>

.user{
    /*height:100%;*/
    /*width: 100%;*/
}
.u{
    height:100%;
    width: 100%;
    /*background: #5c728a;*/
}
   .u>div:first-child{
       height: 50%;
       /*background: #8e42b5;*/
   }
    .touxiang{
        text-align: center;
        height: 100%;
    }
    .touxiang>img{
        border-radius: 50%;
        height: 100%;
    }
    .username,.qian{
        text-align: center;
    }
    .username>div,.qian>div{
        margin: 1% auto;
        width: 80%;
        text-align: center;
        padding: 1% 5%;
        background: rgba(0,0,0,0.5);
        border-radius: 100px;
        color: white;
        font-size: 3vh;
    }
</style>