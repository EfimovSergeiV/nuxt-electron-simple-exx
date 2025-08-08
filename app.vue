<template>
  <div>
    
    <AppHeader />
    <NuxtPage />

  </div>
</template>

<script setup>
  import { onMounted } from 'vue'

  onMounted(async () => {
    const time = await window.ipcRenderer.invoke('app-start-time')
    console.log('App start time:', time)
  })

  onMounted(() => {
    if (window.electronAPI) {
      window.electronAPI.onNavigate((route) => {
        navigateTo(route)
      })
    }
  })
</script>
