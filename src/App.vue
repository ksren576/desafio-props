<template>
  <div id="app">
    <Lista label="Tarea"/>
  </div>
</template>

<script>
import Lista from './components/ListaTodo.vue'

export default {
  name: 'App',
  components: {
    Lista
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
