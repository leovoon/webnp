<template>
  <teleport to="#app">
    <nav v-if="isOpen" ref="modalRef" class="modal">
      <div class="flex justify-end p-3">
        <button class="p-2 text-2xl text-dark-500-600" @click="emit('closeModal')">
          <carbon-close />
        </button>
      </div>
      <ul>
        <slot></slot>
        <li class="text-2xl flex space-x-4">
          <slot name="footer"></slot>
        </li>
      </ul>
    </nav>
  </teleport>
</template>

<script setup lang="ts">
defineProps({ isOpen: Boolean })
const modalRef = ref<null| HTMLElement>(null)
const emit = defineEmits(['closeModal'])
</script>

<style scoped>
nav {
    @apply fixed inset-0 w-full h-screen
     bg-gray-300 opacity-90 dark:(bg-green-800 opacity-90 text-light-200 )
}

ul {
@apply w-full py-6 h-full max-h-[80%] flex flex-col items-center justify-between text-center;
}

</style>
