<script setup lang="ts">
import IconEditTask from '../assets/pen.svg';
import IconDeleteTask from '../assets/delete.svg';

defineProps({
    task: String
});

const emit = defineEmits(['deleteTask', 'editTask']);
</script>

<template>
    <div class="container-task">
        <span>{{ task }}</span>
        <div class="container-actions-task">
            <img :src="IconEditTask" alt="Ícone de Editar" @click="emit('editTask')">
            <img :src="IconDeleteTask" alt="Ícone de Deletar" @click="emit('deleteTask')">
        </div>
    </div>
</template>

<style scoped>
.container-task {
    display: flex;
    align-items: center;
    justify-content: space-between;

    width: 95%;
    height: 3rem;
    padding: 0.5rem;
    border-radius: 0.4rem;

    background-color: var(--vt-c-text-dark-2);
    color: var(--vt-c-text-light-1);
}

.container-actions-task {
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.container-actions-task img {
    width: 2rem;
    height: 2rem;

    cursor: pointer;
}

.container-actions-task img:active {
    scale: 0.9;
}
</style>