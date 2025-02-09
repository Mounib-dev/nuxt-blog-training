<template>
  <div class="container mx-auto max-w-3xl">
    <header class="flex justify-between items-center mt-5">
      <div class="flex items-center space-x-12">
        <div>
          <NuxtLink to="/" class="text-xl font-semibold p-2 hover:bg-gray-200">
            Mounib OUROUA
          </NuxtLink>
        </div>
        <Menu />
      </div>
      <ColorModeSelector />
    </header>
    <main class="p-2 mt-10">
      <slot />
    </main>
  </div>
</template>

<script setup lang="ts">
useHead({
  titleTemplate: "%s - Mounib OUROUA",
  link: [
    {
      rel: "preconnect",
      href: "https://fonts.googleapis.com",
    },
    {
      rel: "stylesheet",
      href: "https://fonts.googleapis.com/css2?family=Roboto&display=swap",
      crossorigin: "",
    },
  ],
});
</script>

<style>
body {
  font-family: "Roboto";
  @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-300;
}
</style>
