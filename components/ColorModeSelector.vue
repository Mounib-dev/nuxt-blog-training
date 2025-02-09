<template>
  <button
    @click="toggleTheme"
    class="hover:bg-gray-200 dark:hover:bg-gray-600 px-2 py-1 text-gray-500 rounded-full sticky top-0 float-right"
  >
    <Icon
      :name="
        themeIcons[`${colorMode.preference === 'light' ? 'dark' : 'light'}`]
      "
      class="size-8 bg-gray-800 dark:bg-yellow-300"
    />
  </button>
</template>

<script setup lang="js">
const colorMode = useColorMode();
const themeIcons = {
  light: 'ic:outline-wb-sunny',
  dark: 'ic:outline-nightlight'
}

const toggleTheme = () => {
    colorMode.preference = colorMode.preference === 'light' ? 'dark' : 'light'
}
</script>

<style scoped></style>
