<template>
  <div id="app">
    <CeilingFan />
  </div>
</template>

<script>
import CeilingFan from './components/CeilingFan.vue'

export default {
  name: 'App',
  components: {
    CeilingFan
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

html {
  background-color: #F1F2F3;
}
</style>
