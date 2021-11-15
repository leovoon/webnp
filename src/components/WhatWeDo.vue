<template>
  <section class="wrapper">
    <div class="flex item-center justify-center text-xl mb-8 ">
      <h1 class="text-2xl sm:text-4xl">
        {{ t('intro.whatwedotitle') }}
      </h1>
    </div>
    <div class="sm:(flex justify-around text-xl)">
      <article>
        <carbon-two-person-lift class="text-4xl" />
        <p> {{ t('intro.whatwedo1') }} </p>
      </article>

      <article>
        <carbon-user-admin class="text-4xl" />
        <p>{{ t('intro.whatwedo2') }}</p>
      </article>

      <article>
        <carbon-laptop class="text-4xl" />
        <p>{{ t('intro.whatwedo3') }}</p>
      </article>
    </div>
  </section>
</template>

<script lang="ts" setup>
const { t } = useI18n()
</script>

<style scoped>
.wrapper {
    @apply -mx-4 px-4 py-20 bg-gradient-to-br dark:(from-green-900 to-green-500) from-green-200 to-green-50
}

article {
    @apply flex flex-col items-center space-y-4 mt-20 sm:( max-w-100 p-4);
}
article p {
  @apply opacity-80;
}
</style>
