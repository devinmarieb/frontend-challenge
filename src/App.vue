<template>
  <div id="app">
    <ListMaker />
  </div>
</template>

<script>
import ListMaker from './components/ListMaker.vue'

export default {
  name: 'App',
  components: {
    ListMaker
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  background: #f1f1f1;
}
#app {
  height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
}
</style>
