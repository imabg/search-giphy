<template>
  <div id="app">
    <myheader />
    <search />
  </div>
</template>

<script>
import myheader from './components/header.vue';
import search from './components/search.vue';

export default {
  name: 'app',
  components: {
    search,
    myheader
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
