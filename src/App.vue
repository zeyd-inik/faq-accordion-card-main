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
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding: 2rem;
    min-height: 100vh;
}
@media (min-width: 768px) {
    .app {
        align-items: center;
    }
}
</style>
