<template>
  <NavbarComp />
  <router-view/>
</template>

<script>
import NavbarComp from './components/NavbarComp.vue'
  export default {
    components: {
      NavbarComp
    }
  }
</script>

<style>
body {
  background: #f5f4f4;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;  
  color: #2c3e50;
  max-width: 600px;
  margin: 0 auto;
  color: #333;
  background: transparent;
}
</style>
