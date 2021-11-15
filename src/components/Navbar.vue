<template>
  <nav :class="{'bg-green-400 bg-opacity-95 dark:(bg-green-900 bg-opacity-95)' : isScrollDown}">
    <logo />
    <ul>
      <li>
        <router-link to="/" :title="t('nav.home')">
          {{ t('nav.home') }}
        </router-link>
      </li>
      <li>
        <router-link to="/cost" :title="t('nav.cost')">
          {{ t('nav.cost') }}
        </router-link>
      </li>
      <li>
        <router-link to="/faqs" :title="t('nav.faqs')">
          {{ t('nav.faqs') }}
        </router-link>
      </li>
      <li>
        <router-link to="/contact" :title="t('nav.contact')">
          {{ t('nav.contact') }}
        </router-link>
      </li>
    </ul>

    <div class="flex space-x-2">
      <button :title="t('button.toggle_dark')" @click="toggleDark()">
        <carbon-moon v-if="isDark" />
        <carbon-sun v-else />
      </button>
      <button
        :title="t('button.toggle_langs')"
        @click="toggleLocales"
      >
        <carbon-language />
      </button>
      <button
        v-show="isMobile"
        :class="{'invisible': isOpen}"
        @click.stop="openModal"
      >
        <carbon-menu />
      </button>
      <burger-modal :is-open="isOpen" @closeModal="handleClose">
        <li v-for="({title, path},idx) in items" :key="idx" class="mobileMenu" @click="handleClose">
          <router-link :to="path" :title="t(`nav.${title}`)">
            {{ t(`nav.${title}`) }}
          </router-link>
        </li>
        <template #footer>
          <li>
            <button
              :title="t('button.toggle_langs')"
              @click="toggleLocales"
            >
              <carbon-language />
            </button>
          </li>
          <li>
            <button :title="t('button.toggle_dark')" @click="toggleDark()">
              <carbon-moon v-if="isDark" />
              <carbon-sun v-else />
            </button>
          </li>
        </template>
      </burger-modal>
    </div>
  </nav>
</template>

<script lang='ts' setup>
import { isDark, toggleDark } from '~/composables'
const { t, availableLocales, locale } = useI18n()

const toggleLocales = () => {
  // change to some real logic
  const locales = availableLocales
  locale.value = locales[(locales.indexOf(locale.value) + 1) % locales.length]
}
const items = [
  {
    title: 'home',
    path: '/',
  },
  {
    title: 'cost',
    path: '/cost',
  },
  {
    title: 'faqs',
    path: '/faqs',
  },
  {
    title: 'contact',
    path: '/contact',
  },

]
const breakpoints = useBreakpoints({
  tablet: 640,
  laptop: 1024,
  desktop: 1280,
})
const { y: windowScrollY } = useWindowScroll()
const isScrollDown = computed(() => windowScrollY.value > 50)
const isMobile = breakpoints.smaller('tablet')
const isOpen = ref(false)
const openModal = () => isOpen.value = true
const handleClose = () => isOpen.value = false
</script>

<style scoped>

nav {
  @apply flex w-full z-1 items-center justify-between transition-colors ease-in  p-4 dark:(text-green-300)  fixed top-0 left-0;
}
nav ul{
@apply hidden items-center space-x-8 sm:(text-xl flex)
}

nav ul li {
  @apply p-2 hover:(ring-green-300 ring-0.8)  dark:(hover:text-light-300);
}

button {
  @apply flex items-center cursor-pointer p-2 dark:text-green-200;
}
li.mobileMenu {
@apply px-4 py-2 text-2xl hover:(ring-2 text-green-600 cursor-pointer) ring-green-600 transition-all ease-out
}
</style>
