<template>
  <figure class="mb-8">
    <faq-splash />
    <em class="text-2xl opacity-75 block my-4 sm:text-4xl">{{ t('faq.title') }}</em>
  </figure>
  <section class="py-10">
    <accordion
      title="some cool title"
    >
      some cool content
    </accordion>
    <accordion
      title="some cool title"
      animation="bottomToTop"
    >
      some cool content
    </accordion>
  </section>
</template>

<script lang='ts' setup>
const { t } = useI18n()
</script>

<style scoped>

</style>
