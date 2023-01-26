<template>
  <main class="py-4 px-8">
    <ContentDoc class="entry | sm:grid" />
  </main>
</template>


<style lang="scss">
.entry {
  grid-template-columns: minmax(33vw, calc(100vh - 10rem)) 1fr;
  grid-template-areas: 
            "a a"
            "b c"
            "b d"
            "b e"
            "b f"
            "b g";
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
  @apply mb-8 text-lg;
}
}

</style>