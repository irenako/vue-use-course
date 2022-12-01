<script setup lang="ts">
import { ref } from 'vue';
import { useRefHistory, useDebouncedRefHistory } from '@vueuse/core';
const newTodo = ref('');
const todos = ref([]);
const { history, undo, redo } = useRefHistory(todos, {
  deep: true,
  capacity: 15,
});
</script>

<template>
  <input type="text" placeholder="New Todo" v-model="newTodo" />
  <button @click="
    todos.unshift(newTodo);
  newTodo = '';
  ">
    Create Todo
  </button>
  <button @click="undo">Undo</button>
  <button @click="redo">Redo</button>
  <ul>
    <li v-for="todo in todos" :key="todo">{{ todo }}</li>
  </ul>
  <br />
  <pre>{{ history }}</pre>
</template>
