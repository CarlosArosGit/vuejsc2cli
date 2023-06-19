<template>
  <div id="app">
    <ComponenteSesionDos />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ComponenteSesionDos from './components/ComponenteSesionDos.vue'

export default {
  name: 'App',
  components: {
    ComponenteSesionDos
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
