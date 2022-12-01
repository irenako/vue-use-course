<script setup lang="ts">
import { ref, computed } from 'vue';
import { useNow, useDateFormat } from '@vueuse/core';
const now = useDateFormat(useNow(), 'HH:mm:ss');
</script>

<template>
  {{ now }}
</template>
