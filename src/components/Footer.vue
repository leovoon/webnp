<template>
  <footer>
    <div class=" mb-4 space-x-8">
      <router-link to="#">
        Privacy Policy
      </router-link>
      <router-link to="#">
        Terms of service
      </router-link>
    </div>
    <p>
      Copyright © webnp {{ year }} <a class="inline-block item mx-2" rel="noreferrer" href="https://github.com/leovoon/webnp" target="_blank" title="GitHub">
        <carbon-logo-github />
      </a>
    </p>
    <p>crafted by leovoon</p>
  </footer>
</template>

<script lang="ts" setup>
// declare a dynamic year variable
const year = new Date().getFullYear()
</script>

<style scoped>
footer {
  @apply text-xs;
}

p {
@apply flex items-center justify-center
}

</style>
