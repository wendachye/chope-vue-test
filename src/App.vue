<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <FloorPlan />
</template>

<script>
import FloorPlan from './components/FloorPlan.vue'

export default {
  name: 'App',
  components: {
    FloorPlan
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
