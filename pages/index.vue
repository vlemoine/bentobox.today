<template>
  <main class="col-span-3 p-8">
    <ContentList v-slot="{ list }">
      <div v-for="article in list" :key="article._path">
        {{ photo(article.body.children) }}
        <h2>{{ article.title }}</h2>
        <p>{{ article.description }}</p>
      </div>
    </ContentList>
  </main>

  
</template>

<script setup>
const photo = (arr) => arr.filter(child => child.tag === 'p')[0]?.children[0]?.props;
</script>