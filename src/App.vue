<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>
<script>
// @ is an alias to /src

export default {
  name: "Home",
  created() {
    function count() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve({ name: "wang" });
        }, 2000);;
      });
    }

    async function fn() {
      var a = await count();
      console.log(a);
    }
    fn();
  },
};
</script>
<style lang="less">
html{
  font-size: 4.2666666vw;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-size: 16px;
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
