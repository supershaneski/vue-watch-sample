<template>
  <div id="app">
    <MyWatch />
  </div>
</template>

<script>
import MyWatch from './components/MyWatch.vue'

export default {
  name: 'App',
  components: {
    MyWatch,
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
