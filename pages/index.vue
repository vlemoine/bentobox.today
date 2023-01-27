<template>
  <main class="p-4 sm:px-8">
    <h1 class="text-lg font-bold mb-4">Past Boxes</h1>
    <div class="gallery | grid gap-4 auto-rows-max">
      <ContentList v-slot="{ list }">
        <template v-for="(article, i) in list" :key="article._path">
          <template v-if="article.title !== 'About'">
            <NuxtLink
              :to="article._path"
              class="border border-pink-700 bg-pink-900 rounded overflow-hidden text-center"
              :style="`order:${order(list, i)}`"
            >
              <img :src="article.img" :alt="article.alt" />
              <h2 class="font-bold my-2">{{ article.title }}</h2>
            </NuxtLink>
          </template>
        </template>
      </ContentList>
    </div>
  </main>
</template>

<script setup>
const order = (arr, i) => arr.length - i;
</script>

<style lang="scss">
.gallery {
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
}
</style>
