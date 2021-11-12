<template>
  <teleport to="#app">
    <nav v-if="isOpen" ref="modalRef" class="modal">
      <div class="flex justify-end p-3">
        <button class="p-2 text-2xl text-dark-500-600" @click="emit('closeModal')">
          <carbon-close />
        </button>
      </div>
      <ul class="flex flex-col items-center text-center ">
        <slot></slot>
        <div class="flex space-x-2 mt-4">
          <slot name="footer"></slot>
        </div>
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
    @apply absolute inset-0 w-full h-full bg-gray-300 opacity-90 dark:(bg-green-800 opacity-90 text-light-200 )
}

</style>
