<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="TP De BioInformatica con lucas sir y el facu"/>
    <custom-map></custom-map>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import CustomMap from './components/CustomMap.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    CustomMap
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
