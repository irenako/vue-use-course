<script setup lang="ts">
import { ref } from 'vue';
import { useRafFn } from '@vueuse/core';
const activePosition = ref(0);
const framesComplete = ref(0);
const { pause, resume, isActive } = useRafFn(() => {
  framesComplete.value++;
  if (framesComplete.value % 7) return;
  if (activePosition.value > -525) {
    activePosition.value -= 75;
  } else {
    activePosition.value = 0;
  }
});
</script>

<template>
  <button @click="isActive ? pause() : resume()">Toggle</button>
  <div
    class="sprite"
    :style="`background-position: ${activePosition}px 50%;`"
  ></div>
</template>

<style>
.sprite {
  background: url(https://freesvg.org/img/1525205509.png) no-repeat;
  width: 75px;
  height: 150px;
}
</style>
