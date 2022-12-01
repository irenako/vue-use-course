<script setup lang="ts">
import { usePageLeave, whenever, usePointer,onLongPress } from '@vueuse/core';
import { ref } from 'vue';
const isLeft = usePageLeave();
const unwatch = whenever(isLeft, () => {
  alert('Are you sure you want to go?');
  unwatch();
});
const pointer = usePointer();
const longBtn = ref(null);
onLongPress(
  longBtn,
  () => {
    alert('Hello world');
  }
);
</script>

<template>
  {{ isLeft }}
  <pre>{{ pointer }}</pre>
  <button ref="longBtn">Click and Hold</button>
</template>
