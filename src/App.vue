<template>
  <div id="app">
    <Space msg="盘古之白"/>
  </div>
</template>

<script>
import Space from './components/Space.vue'

export default {
  name: 'app',
  components: {
    Space
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
  margin-top: 10px;
}
</style>
