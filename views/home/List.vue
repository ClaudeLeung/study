<template>
  <div>
    <ul class="list-wrapper">
      <li class="list" v-for="obj in list" :key="obj.id">
        <img :src="obj.img" alt=""/>
        
        <p>{{obj.name}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
    data(){
        return {
            list:[]
        }
    },
  name: "List",
  created() {
    axios
      .get('http://admin.gxxmglzx.com/tender/test/get_type')
      .then((res) => {
          
         if(res.data.errcode==200){
             this.list=res.data.data
         } 
      })
      .catch((err) => {
        console.log(err)

      });
  },
};
</script>

<style lang="scss" scoped>
.list-wrapper {
  display: flex;
  text-align: center;
  flex-wrap: wrap;
  margin-bottom: 0.3rem;
  .list {
    width: 20%;
    img {
      width: 70%;
    padding: 0.2rem;

    }
  }
}
</style>