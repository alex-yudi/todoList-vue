<script setup lang="ts">
import IconCheckList from '../assets/checklist-svgrepo-com.svg';

</script>

<template>
    <header>
        <img :src="IconCheckList" alt="Ícone de Checklist">
        <h1>Simple Todo List</h1>
    </header>
</template>

<style scoped>
header {
    display: flex;
    align-items: center;
    justify-content: center;

    width: 25rem;
    padding: 10px;
    gap: 2rem;
    margin: 0 auto;
    border-radius: 0.5rem;

    background-color: var(--vt-c-text-dark-2);
    color: var(--vt-c-text-light-1);
}

header>img {
    width: 50px;
    height: 50px;
}
</style>