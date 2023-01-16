<script setup>
import { RouterView } from 'vue-router';
</script>

<template>
    <div class="app">
        <RouterView />
    </div>
</template>

<style>
.app {
    background-image: linear-gradient(180deg, var(--Soft-violet), var(--Soft-blue));
    height: 100vh;
    overflow: auto;
    display: flex;
    justify-content: center;
    align-items: flex-start;
}
</style>
