<script setup>
import { ref } from 'vue';
import { useClipboard } from '@vueuse/core';

const textToCopy = ref('Hello');
const { copy, copied, text, isSupported } = useClipboard({
  copiedDuring: 3000,
});
</script>

<template>
  <input type="text" v-model="textToCopy" />
  <button v-if="isSupported" @click="copy(textToCopy)">
    {{ copied ? 'Copied' : 'Copy' }}
  </button>
  {{ text }}
</template>