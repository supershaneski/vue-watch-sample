<template>
  <div id="app">
    <Watch />
  </div>
</template>

<script>
import Watch from './components/Watch.vue'

export default {
  name: 'App',
  components: {
    Watch,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  /*background-color: #000;*/
  position: relative;
  width: 200px;
  height: 200px;
}
</style>
