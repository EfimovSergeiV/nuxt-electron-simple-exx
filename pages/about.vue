<template>
  <div>
    <h1>About Page</h1>
    <p>This is the about page of your Nuxt application.</p>

    <nuxt-link :to="{ name: 'index' }">Go to About Page</nuxt-link>

    <div class="mt-6">
      <ChartsSection />
    </div>
    
  </div>
</template>
