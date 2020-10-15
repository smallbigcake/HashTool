<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HashTool msg="Welcome to Hash Tool App"/>
</template>

<script>
import HashTool from './components/HashTool.vue'


export default {
  name: 'App',
  components: {
      HashTool
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
