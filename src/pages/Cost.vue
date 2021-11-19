<template>
  <figure class="mb-8">
    <cost-splash />
    <em class="my-4 opacity-75 text-2xl block sm:text-4xl">{{ t('cost.title') }}</em>
  </figure>
  <h1 class=" text-center text-xl mb-12 px-6">
    {{ t('cost.titleDesc') }}
  </h1>
  <div class=" space-y-6 text-center px-6 mb-12 text-dark-800 text-opacity-70 dark:text-green-400">
    <h2>
      {{ t('cost.titleDesc2') }}
    </h2>
    <h2>
      {{ t('cost.titleDesc2i') }}
    </h2>
  </div>
  <div class="-mx-4 bg-gradient bg-gradient-to-tr from-green-300 via-green-300 to-yellow-300 dark:(from-dark-400 to-dark-900) space-y-4 p-6 gap-4 sm:flex-row flex flex-col justify-center items-center ">
    <cost-card>
      <template #icon>
        <carbon-volume-file-storage class="dark:text-green-200" />
      </template>
      <template #title>
        {{ t('cost.cardFreeT') }}
      </template>
      {{ t('cost.cardFree') }}
      <template #tag>
        {{ t('cost.cardFreeTag') }}
      </template>
    </cost-card>
    <cost-card>
      <template #icon>
        <carbon-bare-metal-server class="dark:text-green-200" />
      </template>
      <template #title>
        {{ t('cost.cardHostT') }}
      </template>
      {{ t('cost.cardHost') }}
      <template #tag>
        {{ t('cost.cardHostTag') }}
      </template>
    </cost-card>
    <cost-card>
      <template #icon>
        <carbon-devices class="dark:text-green-200" />
      </template>
      <template #title>
        {{ t('cost.cardCmsT') }}
      </template>
      {{ t('cost.cardCms') }}
      <template #tag>
        {{ t('cost.cardCmsTag') }}
      </template>
    </cost-card>
  </div>

  <section class="py-12 mb-8 space-y-8 flex flex-col items-center sm:(flex-row justify-around items-center space-y-0)">
    <h1 class="text-xl sm:text-3xl">
      {{ t('intro.getnow') }}
    </h1>
    <router-link to="/contact" class="btn">
      {{
        t('intro.getInTouch')
      }}
    </router-link>
  </section>
</template>

<script setup lang='ts'>
const { t } = useI18n()
</script>
