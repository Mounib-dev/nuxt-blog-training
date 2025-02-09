<template>
  <ContentRenderer :value="post" />
</template>

<script setup>
const route = useRoute();
const path = route.path;
const { data: post } = await useAsyncData(path, () => {
  return queryCollection("blog").path(path).first();
});
</script>

<style scoped></style>
