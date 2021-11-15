<script setup lang="ts">

const { t } = useI18n()
</script>

<template>
  <figure class="mb-8">
    <splash />
    <em class="text-2xl opacity-75 block my-4 sm:text-4xl">{{ t('intro.desc') }}</em>
  </figure>

  <section class="mb-8 py-10 sm:(flex items-center text-center justify-between p-20)">
    <div class="flex item-center justify-center text-xl mb-8">
      <h1 class="text-2xl sm:text-4xl">
        {{ t('intro.whyfreetitle') }}
      </h1>
      <carbon-query class="inline-block mx-4 text-xl sm:text-4xl" />
    </div>
    <p class="opacity-75 sm:(text-2xl text-center w-[60%])">
      {{
        t('intro.whyfree')
      }}
    </p>
  </section>

  <what-we-do />

  <section class="py-12 mb-8 space-y-8 flex flex-col items-center sm:(flex-row justify-around items-center space-y-0)">
    <h1 class="text-xl sm:text-3xl">
      {{ t('intro.getnow') }}
    </h1>
    <router-link to="/contact" class="btn">
      {{
        t('intro.getInTouch')
      }}
    </router-link>

    <router-link to="/contact" class="btn">
      {{
        t('intro.getVol')
      }}
    </router-link>
  </section>
</template>
