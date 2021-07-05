<template>
  <div id="nav">
    <router-link to="/">About</router-link> |
    <router-link to="/about">Newsfeed</router-link>
  </div>
  <router-view/>
</template>

<script lang ="ts">

export default {
  name: 'App',
  components: {},
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body{
  margin: 0;
  background: #eee;
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
</style>
