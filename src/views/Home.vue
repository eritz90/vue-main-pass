<template>
  <div class="home">
    <HelloWorld msg=" Welcome to my Homepage!"/>
    <h3>made with Vue.js</h3>
    <img alt="Vue logo" src="../assets/2X2.jpg">
    <h2>made by Edrei Ritz C. Sipalay</h2>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default defineComponent({
  name: 'Home',
  components: {
    HelloWorld,
  },
});
</script>

<style scoped>
h2 {
  padding-top:0px;
  font-size: 15px;
  font-style: italic;
}
</style>
