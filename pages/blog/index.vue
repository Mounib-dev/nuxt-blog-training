<template>
  <ul>
    <li
      v-for="post in posts"
      :key="post.id"
      class="p-2 hover:border hover:border-gray-700 rounded-md w-fit dark:hover:border dark:hover:border-zinc-100"
    >
      <NuxtLink :to="post.path" class="link">{{ post.title }}</NuxtLink>
    </li>
  </ul>
</template>

<script setup lang="ts">
useSeoMeta({
  title: "Blog",
  description: "Mounib blog sharing insights",
  ogTitle: "Home",
});

useHead({
  htmlAttrs: {
    lang: "en",
  },
});
const { data: posts } = await useAsyncData("blog", () => {
  return queryCollection("blog").all();
});
console.log(posts.value);
</script>

<style scoped></style>
