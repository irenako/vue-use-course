<script setup lang="ts">
import useAlertFavicon from '../composables/useIconFavicon';
const vueFavicon =
  'https://raw.githubusercontent.com/vueschool/useAlertFavicon-boilerplate/main/public/favicon.ico';
const vueSchoolFavicon =
  'https://raw.githubusercontent.com/vueschool/useAlertFavicon/main/public/vue-school-favicon.png';
const { alert, favicon, cancel } = useAlertFavicon(vueFavicon, {
  speed: 500,
  emoji: '👻',
});
</script>

<template>
  <button @click="alert">Alert</button>
  <button @click="favicon = vueSchoolFavicon">Change</button>
  <button @click="cancel">Cancel</button>
</template>