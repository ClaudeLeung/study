<template>
  <div>
    <h2 class="head">附近的商家</h2>
    <!-- 商家列表 -->
    <ul class="list-box">
      <li class="list" v-for="obj in list" :key="obj.id">
        <img
          class="img"
          :src="obj.img"
          alt=""
        />
        <div class="info">
          <p class="title">{{obj.name}}</p>
          <div class="middle">
            <span class="yellow">4.8 </span>
            <span>月销{{obj.num}}+</span>
            <div class="right"><span>{{obj.minute}}分钟 </span> <span>{{obj.distance}}</span></div>
          </div>
          <!-- 配送费 -->
          <span>起送¥{{obj.price}} </span>
          <span>配送¥5</span>
          <span class="give">美团专送</span>
        </div>
      </li>
       <li class="list">
        <img
          class="img"
          src="https://p0.meituan.net/waimaipoi/836ce31a4037f8bc8cf6cef9415fde4b30720.jpg@228h"
          alt=""
        />
        <div class="info">
          <p class="title">南京灌汤包(电缆街店)</p>
          <div class="middle">
            <span class="yellow">4.8 </span>
            <span>月销1000+</span>
            <div class="right"><span>36分钟 </span> <span>238米</span></div>
          </div>
          <!-- 配送费 -->
          <span>起送¥20 </span>
          <span>配送¥5</span>
          <span class="give">美团专送</span>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{list:[]} 
    },
  name: "StoreList",
  methods:{
      getStoreList(){
       axios.get('http://admin.gxxmglzx.com/tender/test/get_store?current=1&size=10').then((res)=>{
           this.list= res.data.data.list;
           
       }).catch((err)=>{
            console.log(err)
       })
      }
  },
  created(){
       this.getStoreList();
  }
};
</script>

<style lang="scss" scoped>
.head {
  padding: 0.1rem;
  font-size: 150%;
  font-weight: bolder;
  text-align: center;
}
.list-box {
  padding: 0 10px;
}
.list {
  display: flex;
  margin: 10px 0 25px;
  .img {
    width: 76px;
    height: 67px;
    margin-right: 10px;
    border:1px solid #e4e4e4a
  }
  .info {
      font-size: 11px;
      color: #333;
    flex: 1;
    .title {
      font-size: 17px;
      font-weight: 600;
    }
    .yellow {
      color: orange;
    }
    .right{
        float: right;
    }
    .middle{
        padding: 5px 0;
    }
    .give{
        float: right;
        background: yellow;
        border-radius: 10px;
    }
  }
}
</style>