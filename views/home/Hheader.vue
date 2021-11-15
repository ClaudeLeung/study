<template>
  <div class="h-container">
    <div class="positionphoto">
      <img class="incont" src="../photos/401.png" alt="" />
    </div>
    <h2>哈尔滨市南岗区</h2>
    <input class="search" placeholder="蜜雪冰城" type="text" />
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.h-container {
  height: 0.8rem;
  width: 100%;
  line-height: 0.8rem;
  background: orange;
  font-size: 5px;
  color: black;
  font-size: 14px;
  display: flex;
  .positionphoto {
    width: 0.5rem;
    height: 0.5rem;
    margin-left: 0.3rem;

    .incont {
      width: 100%;
      height: 100%;
    }
  }
  .search{
      margin-left: 0.6rem;
      border-radius: 8px;
      height: 80%;
      margin-top: 0.1rem;
  }
}
</style>