<template>
  <div id="app">
    <FlipbookComponent/>
  </div>
</template>

<script>
import FlipbookComponent from './components/FlipbookComponent.vue'

export default {
  name: 'App',
  components: {
    FlipbookComponent
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
