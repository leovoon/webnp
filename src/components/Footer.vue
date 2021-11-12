<template>
  <footer class="text-xl mt-6">
    <a class="icon-btn mx-2" rel="noreferrer" href="https://github.com/leovoon/webnp" target="_blank" title="GitHub">
      <carbon-logo-github />
    </a>
    <p class="text-sm">
      Copyright © webnp {{ year }}
    </p>
  </footer>
</template>

<script lang="ts" setup>
// declare a dynamic year variable
const year = new Date().getFullYear()
</script>
