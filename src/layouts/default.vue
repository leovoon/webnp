<template>
  <header class="flex items-center justify-between p-4">
    <Navbar />
  </header>
  <main class="px-4 py-10 text-center text-gray-700 dark:text-gray-200">
    <router-view />
    <Footer />
  </main>
</template>
