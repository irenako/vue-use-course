<script setup lang="ts">
import { useIntervalFn } from '@vueuse/core';
const { pause, resume, isActive } = useIntervalFn(
  () => console.log('Hello world'),
  100
);
</script>

<template>
  <button @click="isActive ? pause() : resume()">
    {{ isActive ? 'Pause' : 'Resume' }}
  </button>
</template>
