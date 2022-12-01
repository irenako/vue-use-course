<script setup>
import { ref, watch } from 'vue';
import { useMagicKeys, whenever } from '@vueuse/core';
const { ctrl_a, current } = useMagicKeys();
whenever(ctrl_a, (pressed) => console.log(pressed));
</script>

<template>
  {{ current }}
</template>