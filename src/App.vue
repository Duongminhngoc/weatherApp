<template>
  <div id="app">
    <WeatherApp/>
  </div>
</template>

<script>
import WeatherApp from './components/WeatherApp.vue'

export default {
  name: 'App',
  components: {
    WeatherApp
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
body {
  background-color: #5C4084;
}
</style>
