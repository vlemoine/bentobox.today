<template>
  <main class="py-4 px-8">
    <ContentDoc class="entry | sm:grid" />
  </main>
</template>


<style lang="scss">
.entry {
  grid-template-columns: minmax(33.3vw, 1fr) 1fr;
  grid-template-areas: 
            "a a"
            "b c"
            "b d"
            "b e";
  grid-column-gap: 2rem;
  h1 {
  @apply font-bold mb-4 text-2xl;
  grid-area: a;
}
h2 {
  @apply font-bold mb-2 text-xl;
}
p:has(img) {
  grid-area: b;
}
ul {
  @apply text-lg;
}
}

</style>