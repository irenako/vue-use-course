<script lang="ts" setup>
import { useVModel } from '@vueuse/core';
const props = defineProps({
  modelValue: Number,
});
const emit = defineEmits(['update:modelValue']);
const data = useVModel(props, 'modelValue', emit);
</script>

<template>
  <button @click="data--">-</button>
  <input type="number" v-model="data" />
  <button @click="data++">+</button>
</template>

<style>
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
