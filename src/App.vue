<template>
  <div id="app">
    <ChartComp />
  </div>
</template>

<script>
import ChartComp from './components/ChartComp.vue'

export default {
  name: 'App',
  components: {
    ChartComp
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
