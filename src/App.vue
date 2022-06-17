<script setup lang="ts">
useHead({
  title: 'CloudApp',
  meta: [
    { name: 'description', content: 'Unopinionated Cloud Solution' },
    {
      name: 'theme-color',
      content: computed(() => isDark.value ? '#00aba9' : '#ffffff'),
    },
  ],
  link: [
    {
      rel: 'icon',
      type: 'image/svg+xml',
      href: '/logo.svg'
    },
  ],
})
</script>

<template>
  <Hero />
  <RouterView />
  <Fetch endpoint="shop/" />
</template>
