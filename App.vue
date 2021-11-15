<template>
  <div id="app">
    <h2>APP主组件</h2>
    <button @click="fn">&lt;返回</button>
    <button @click="goHome">首页</button>
    <button @click="goTest">test1</button>

    <router-link to="/home">首页</router-link>
    <router-link to="/about">关于我们</router-link>
    <router-link :to="{ path: '/test1', query: { id: 10, name: 'zs' } }"
      >test1</router-link
    >
    <router-link :to="{ name: 'test2', params: { id: 99 } }">test2</router-link>
    <router-link to="/test3/100/Mike">test3</router-link>
    <router-link to="/abc">abc</router-link>
    <transition name="fade">
      <router-view></router-view>
    </transition>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
.fade-enter {
  transform: translateX(100%);
}
.fade-enter-to {
  transform: translateX(0%);
}
.fade-enter-active {
  transition: transform 2s ease;
}
.fade-leave {
  transform: translateX(0);
}
.fade-leave-to {
  transform: translateX(-100%);
}
.fade-leave-active {
  transition: transform 2s ease;
}
</style>
<script>
export default {
  name: "app",
  methods: {
    fn() {
      this.$router.go(-1);
    },
    goHome(){
      this.$router.push("/home");
    },
    goTest(){
      this.$router.push({path:'/test1',query:{id:888,name:'List'}})
    }
  },
};
</script>
