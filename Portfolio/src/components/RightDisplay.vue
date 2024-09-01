<script setup lang="ts">
import Languages from './Languages.vue'
</script>

<template>
    <div class="right-column">
        <h2>Programming languages</h2>
        <Languages/>
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
    }
</style>