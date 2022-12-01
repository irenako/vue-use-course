<script setup lang="ts">
import { refAutoReset } from '@vueuse/core';
const showAlert = refAutoReset(false, 3000);
showAlert.value = true;
</script>

<template>
  <transition appear>
    <div v-if="showAlert" class="alert">Your post has been saved</div>
  </transition>
  <button @click="showAlert = true">Show Alert</button>
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
