<script setup>
import { ref } from 'vue';
import { onKeyStroke } from '@vueuse/core';
const controls = {
  ArrowDown: () => (position.value.y += 5),
  ArrowUp: () => (position.value.y -= 5),
  ArrowRight: () => (position.value.x += 5),
  ArrowLeft: () => (position.value.x -= 5),
};
const position = ref({ x: 0, y: 0 });
onKeyStroke(Object.keys(controls), (e) => {
  e.preventDefault();
  controls[e.key]();
});
</script>

<template>
  <div class="ball"></div>
</template>

<style lang="css">
.ball {
  width: 10px;
  height: 10px;
  background: red;
  border-radius: 50%;
  position: absolute;
  top: v-bind(position.y + 'px');
  left: v-bind(position.x + 'px');
}
</style>