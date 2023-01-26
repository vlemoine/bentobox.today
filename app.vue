<template>
  <div class="h-full flex flex-col">
    <Html lang="en-us"></Html>
    <Head>
      <Title>bentobox.today</Title>
    </Head>
    <Body class="dark:bg-gray-900 text-black/80 dark:text-white"></Body>
    <header class="p-4 flex border-b border-b-pink-700 sticky top-0 text-3xl bg-pink-900">
      <a href="/">🍱 bentobox.today</a>
    </header>
    <div class="grid grid-cols-4 grow">
      <nav class="bg-red-500/10 p-4">
        <ContentNavigation v-slot="{ navigation }">
          <ul class="sticky top-20">
            <li v-for="link of navigation" :key="link._path">
              <NuxtLink :to="link._path">🎀 {{ link.title }}</NuxtLink>
            </li>
          </ul>
        </ContentNavigation>
      </nav>
      <NuxtPage />
    </div>
  </div>
</template>

<style>
html,
body,
#__nuxt {
  height: 100%;
}
</style>
