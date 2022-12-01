<script setup lang="ts">
import { ref } from 'vue';
import { useTimeout } from '@vueuse/core';
const { ready, start, stop, isPending } = useTimeout(3000, {
  controls: true,
});
</script>

<template>
  {{ ready }}
  <transition appear>
    <div v-if="isPending" class="alert">
      Your post has been saved
      <button @click="stop">x</button>
    </div>
  </transition>
  <button @click="start">start timeout</button>
</template>

<style>
.v-enter-active,
.v-leave-active {
  transition: all 0.2s ease;
}

.v-enter-from,
.v-leave-to {
  transform: translateY(-10px);
  opacity: 0;
}
</style>
