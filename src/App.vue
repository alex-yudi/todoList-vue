<script setup lang="ts">
import { ref } from 'vue';
import Header from './components/Header.vue';
import Task from './components/Task.vue';

const taskList = ref<string[]>([]);
const taskValue = ref('');

const handleNewTask = () => {
  taskList.value.push(taskValue.value);
}
const handleDeleteTask = (task: string) => {
  taskList.value = taskList.value.filter((taskItem) => taskItem !== task);
}
const handleEditTask = (task: string) => {
  taskValue.value = task;
  handleDeleteTask(task);
}
</script>

<template>
  <Header>

  </Header>

  <main>
    <div class="container-input-task">
      <input type="text" v-model="taskValue">
      <button type="button" @click="handleNewTask()">
        Adicionar
      </button>
    </div>
    <div class="container-tasks">
      <Task v-for="task in taskList" :key="task" :task="task" @delete-task="handleDeleteTask(task)"
        @edit-task="handleEditTask(task)" />
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  margin-top: 1rem;
  gap: 2rem;

  width: 100%;
  min-height: 90%;
}

.container-tasks {
  display: flex;
  flex-direction: column;
  align-items: center;

  min-height: 25rem;
  width: 50rem;
  gap: 0.5rem;
  border-radius: 1rem;
  padding: 1rem;

  background-color: var(--vt-c-text-dark-2);
}

.container-input-task {
  display: flex;
  align-items: center;
  justify-content: center;

  gap: 1rem;

  width: 100%;
  height: 50px;
}

.container-input-task>input {
  width: 51.5%;
  height: 100%;

  border-radius: 0.4rem;

  font-size: 1rem;
  padding: 0.5rem;
}

.container-input-task>input:focus {
  outline: none;
}

.container-input-task>button {
  width: 10%;
  height: 100%;

  border-radius: 0.4rem;

  font-size: 1rem;
  padding: 0.5rem;

  background-color: green;

  border: none;
  outline: none;

  cursor: pointer;
}

.container-input-task>button:active {
  background-color: darkgreen;
}
</style>
