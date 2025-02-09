<template>
  <button
    @click="toggleTheme"
    class="hover:bg-gray-200 dark:hover:bg-gray-600 px-2 py-1 text-gray-500 rounded-full"
  >
    {{ themeIcons[`${colorMode.preference === "light" ? "dark" : "light"}`] }}
  </button>
</template>

<script setup lang="js">
const colorMode = useColorMode();
const themeIcons = {
  light: '🌕',
  dark: '🌑'
}

const toggleTheme = () => {
    colorMode.preference = colorMode.preference === 'light' ? 'dark' : 'light'
}
</script>

<style scoped></style>
