<template>
  <div class="h-full flex flex-col">
    <Html lang="en-us"></Html>
    <Head>
      <Link rel="icon" href="https://fav.farm/🍱"></Link>
      <Title>bentobox.today</Title>
    </Head>
    <Body class="bg-gray-900 text-white"></Body>
    <header
      class="p-4 flex border-b border-b-pink-700 sticky top-0 left-0 text-3xl bg-pink-900"
    >
      <a href="/">🍱 bentobox.today</a>
    </header>
    <div class="grid grid-cols-[auto_1fr] grow overflow-x-hidden">
      <nav class="bg-red-500/10 p-2 sm:p-4">
        <ContentNavigation v-slot="{ navigation }">
          <ul class="sticky top-2 sm:top-4 flex flex-col-reverse gap-2">
            <li
              v-for="link of navigation"
              :key="link._path"
              :class="{ 'order-first mt-2': link.title === 'About' }"
            >
              <NuxtLink :to="link._path" class="text-sm sm:text-base"
                >🎀 {{ link.title }}</NuxtLink
              >
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
