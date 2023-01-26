<template>
  <main class="gallery | p-8 grid gap-4 auto-rows-max">
    <ContentList v-slot="{ list }">
      <template v-for="(article, i) in list" :key="article._path">
        <template v-if="article.title !== 'About'">
          <NuxtLink
            :to="article._path"
            class="border border-pink-700 bg-pink-900 rounded overflow-hidden text-center"
            :style="`order:${order(list, i)}`"
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
const order = (arr, i) => arr.length - i;
</script>

<style>
.gallery {
  grid-template-columns: repeat(auto-fill,  minmax(16rem, 1fr));
}
</style>
