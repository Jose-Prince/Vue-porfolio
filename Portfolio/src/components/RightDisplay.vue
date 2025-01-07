<script setup lang="ts">
    import Languages from './Languages.vue';
    import Jobs from './Jobs.vue';
    import Redirect from './ProjectRedirection.vue';

</script>

<template>
  <div class="right-column">
    <div>
      <h2>Programming languages</h2>
      <Languages />
    </div>
    <Jobs />
    <Redirect label="What I am working on?" />  <!-- Pasa el prop "label" correctamente -->
    <Redirect label="What I have done?" /> <!-- O proporciona un valor por defecto -->
  </div>
</template>


<style>
    .right-column {
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 100%;
        align-items: center;
        background-color: black;
        gap: 50px;
    }
</style>