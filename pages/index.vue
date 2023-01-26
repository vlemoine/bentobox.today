<template>
  <main class="col-span-3 p-8 grid grid-cols-3 gap-4 auto-rows-max">
    <ContentList v-slot="{ list }">
      <template v-for="article in list" :key="article._path">
        <template v-if="article.title !== 'About'">
          <NuxtLink
            :to="article._path"
            class="border border-pink-700 bg-pink-900 rounded overflow-hidden text-center"
          >
            <img
              :src="photo(article.body.children).src"
              :alt="photo(article.body.children).alt"
            />
            <h2 class="font-bold my-2">{{ article.title }}</h2>
          </NuxtLink>
        </template>
      </template>
    </ContentList>
  </main>
</template>

<script setup>
const photo = (arr) =>
  arr.filter((child) => child.tag === "p")[0]?.children[0]?.props;
</script>
