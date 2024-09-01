<script setup lang="ts">
  import NameDisplay from "./Namedisplay.vue";
  import Elements from "./ElementsGrid.vue"
</script>

<template>
  <div class='left-column'>
    <NameDisplay/>
    <Elements/>
  </div>
</template>

<style>
  .left-column {
    position: relative;
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    z-index: 2;
  }
</style>
