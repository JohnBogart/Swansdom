<template>
  <div id="app">
    <h1>Swansdom</h1>
    <Quote />
    <img src="./assets/RONSWANSON.png" />
  </div>
</template>

<script>
import Quote from './components/Quote.vue'

export default {
  name: 'App',
  components: {
    Quote
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
