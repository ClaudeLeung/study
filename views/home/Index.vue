<template>
  <div>
    <!-- header  -->
    <Hheader></Hheader>
    <!-- list  -->
    <List></List>
    <!-- storelist  -->
    <StoreList></StoreList>
  </div>
</template>

<script>
import Hheader from "./Hheader.vue";
import List from "./List.vue";
import StoreList from "./StoreList.vue";

export default {
  components: {
    Hheader,
    List,
    StoreList,
  },
};
</script>

<style lang="scss" scoped>
</style>