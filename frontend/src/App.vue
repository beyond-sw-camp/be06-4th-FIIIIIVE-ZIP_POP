<template>
  <testTemplate></testTemplate>
</template>

<script>
import testTemplate from './components/testTemplate.vue'

export default {
  name: 'App',
  components: {
    testTemplate
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
