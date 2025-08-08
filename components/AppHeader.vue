<template>
  <header>
    <div class="container mx-auto px-4">
      <nav class="flex flex-row gap-4">

        <nuxt-link :to="{ name: 'index' }" class="text-red-500">Home</nuxt-link>
        <nuxt-link :to="{ name: 'about' }" class="text-red-500">About</nuxt-link>

      </nav>
    </div>

  </header>
</template>
