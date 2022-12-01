<script setup lang="ts">
import { useLocalStorage, useSessionStorage } from '@vueuse/core';
const name = useLocalStorage('name', 'Daniel');
const favoriteFood = useSessionStorage('favoriteFood', 'ice cream');
</script>

<template>
  <input type="text" v-model="name" />
  <input type="text" v-model="favoriteFood" />
</template>
