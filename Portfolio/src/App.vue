<script setup lang="ts">
import Left from './components/LeftDisplay.vue'
import Center from './components/CenterDisplay.vue'
import Right from './components/RightDisplay.vue'
</script>

<template>
  <div class="grid-display">
    <Left/>
    <Center/>
    <Right/>
  </div>
</template>

<style scoped>
  .grid-display {
    display: grid;;
    grid-template-columns: 25% 50% 25%;
    grid-template-rows: 100%;
    height: 94vh;
  }
</style>
