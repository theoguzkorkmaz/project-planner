<template>
  <nav class="main-nav">
    <router-link :to="{name: 'Home'}">Projects</router-link>
    <router-link :to="{name: 'AddProject'}">Add New Project</router-link>
  </nav>
</template>

<script>
export default {

}
</script>

<style scoped>
  .main-nav {
    text-align: center;
    margin: 40px auto;
  }
  .main-nav a {
    display: inline-block;
    text-decoration: none;
    margin: 0 10px;
    color: #777777ab;
    font-size: 18px;
    text-transform: uppercase;
    font-weight: bold;
  }
  a.router-link-active {
    border-bottom: 4px solid rgba(255, 0, 0, 0.325);    
  }
</style>