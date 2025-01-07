<script setup lang="ts">
import NavBar from './components/NavBar.vue'
import Home from './pages/Home.vue'
</script>

<template>
  <div class="portfolio-style">
    <NavBar/>
    <router-view />
  </div>
</template>

<style scoped>
  .portfolio-style {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100vh;
    margin: 0;
    background-color: #FAFAFA;
  }

</style>
