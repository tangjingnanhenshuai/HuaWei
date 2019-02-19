<template>
    <div class="appson">
      <div class="divs">
        <p class="ap" @click="go" ><img src="../assets/img/yjt.gif" alt=""></p>
        <p>商品列表</p>
        <p class="ap" href="javascript:void(0)"></p>
      </div>

      <div class="con">
        <div>
          <ul class="uls">
            <hw-xp-new-product :key="index" v-for="(a,index) in data.products" :data="a"></hw-xp-new-product>
          </ul>
        </div>

        <img class="imgh" src="../../static/img/54022ea0-765a-45ff-82ea-253036f24592.png" alt="">
      </div>
    </div>
</template>

<script>
  import HwXpNewProduct from "../components/HwXp/HwXpNewProduct"
  import data from "../api-server/data/xp"
    export default {
        name: "HwXp",
        components:{
          HwXpNewProduct
        },
        data(){
          return{
            data
          }
        },
      methods:{
        go(){
          this.$router.go(-1);
        }
      }
    }
</script>

<style scoped>
  .appson{
    width: 100%;
    background: #ffffff;
    height: 100%;
    display: flex;
    flex-direction: column;
  }

.con{
  width: auto;
  padding: .06rem .15rem 0;
  flex: 1;
  overflow-x: hidden;
  overflow-y: auto;
}
.uls{
  height: 100%;
  overflow-x: hidden;
  overflow-y: auto;
}
.uls>a:nth-child(2n){
  margin-right: 0;
}
.uls>a:nth-child(2n+1){
  margin-right: 2%;
}
  .imgh{
    display: block;
    width: 100%;
    /*padding: 0;*/
    height:.3rem;
    background: #f1f1f1;
  }
.ap{
  width:5%;
  font-size: .22rem;
  color: #000;
  /*background: yellow;*/
}
.divs{
  /*width: 100%;*/
  height: .5rem;
  display: flex;
  justify-content: space-between;
  align-items: center
}
p{
  width: 60%;
  font-size: .2rem;
  color: #333333;
  text-align: center;
  /*background: red;*/
}
</style>
