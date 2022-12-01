<script setup lang="ts">
import { ref, computed } from 'vue';
import { useWindowSize, useWindowFocus, useIntersectionObserver } from '@vueuse/core';
const focused = useWindowFocus();
const { width, height } = useWindowSize();
const h1 = ref(null);
const h1IsVisible = ref(false);
useIntersectionObserver(h1, ([{ isIntersecting }]) => {
  h1IsVisible.value = isIntersecting;
});
</script>

<template>
{{ width }} x {{ height }}
{{ focused }}

<div style="height: 200px; overflow: scroll; border: 1px solid black">
  <h1 :class="{ 'fade-in': h1IsVisible }" style="margin: 300px 0" ref="h1">
    Hello world
  </h1>
</div>
{{ h1IsVisible }}
</template>

<style>
@keyframes fadeIn {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}

.fade-in {
  animation: fadeIn ease 1s;
}
</style>
