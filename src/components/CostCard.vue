<template>
  <div class="w-full bg-white dark:(bg-gradient bg-gradient-to-br from-blue-gray-700 ring-gray-400 ring-1 ring-opacity-20 to-blue-gray-900 shadow-dark-700)  text-dark-50  transform transition-transform ease-in hover:-translate-y-1 rounded-md shadow-lg ring-px ring-dark-50 flex flex-col space-y-6 max-w-[20rem] p-6 justify-center items-center">
    <div class="flex flex-col items-center gap-3">
      <span class="text-3xl ">
        <slot name="icon"></slot>
      </span>
      <span class="text-2xl dark:text-light-200">
        <slot name="title"></slot>
      </span>
    </div>
    <p class="font-thin text-dark-50 dark:text-gray-300">
      <slot></slot>
    </p>
    <p class="text-2xl font-bold dark:text-green-200">
      <slot name="tag"></slot>
    </p>
  </div>
</template>

<script setup lang='ts'>

</script>
