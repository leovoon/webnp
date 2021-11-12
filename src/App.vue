<script setup lang="ts">
// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'webnp',
  meta: [
    { name: 'description', content: 'free site for non-profits and charities' },
  ],
})
</script>

<template>
  <router-view />
</template>
