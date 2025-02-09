<template>
  <p class="mb-10">Take a look at my GitHub Projects</p>
  <section v-if="error">Something went wrong... try again!</section>
  <section v-else>
    <ul class="grid grid-cols-1 gap-4">
      <li
        v-for="repository in data"
        :key="repository.id"
        class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono"
      >
        <a :href="repository.html_url" target="_blank">
          <div class="flex items-center justify-between">
            <div class="font-semibold">{{ repository.name }}</div>
            <div>{{ repository.id }}</div>
          </div>
        </a>
      </li>
    </ul>
  </section>
</template>

<script setup lang="js">
const { error, data } = await useFetch(
  "https://api.github.com/users/Mounib-dev/repos"
);

const repos = computed(() =>
  data.value
    .filter((repo) => repo.description)
    .sort((a, b) => {
      return a.description - b.description;
    })
);
</script>

<style scoped></style>
