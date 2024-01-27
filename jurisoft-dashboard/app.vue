<template>
  <NuxtLayout />
</template>

<script setup lang="ts">
import { useHead } from 'unhead'

useHead({
  title: 'Dashboard - Jurisoft',
  meta: [
    { name: 'description', content: 'My amazing site.' }
  ],
  bodyAttrs: {
    class: 'test'
  },
  script: [ { innerHTML: 'console.log(\'Hello world\')' } ]
})
</script>

<style lang="scss">
// resetar css
@import "@/assets/scss/reset.scss";
@import "@/assets/scss/main.scss";
</style>
