<template>
  <div>
    <router-view />
  </div>
</template>

<script>
import Home from './views/Home.vue'
export default {
  name: 'App',
  components: { Home },
  mounted() {
    const isUserColorTheme = localStorage.getItem('color-theme')
    if (isUserColorTheme === 'system' || isUserColorTheme === null) {
      const isOsColorTheme = window.matchMedia('(prefers-color-scheme: dark)')
        .matches
        ? 'dark'
        : 'light'

      document.documentElement.setAttribute('color-theme', isOsColorTheme)
    } else {
      document.documentElement.setAttribute('color-theme', isUserColorTheme)
    }
  },
}
</script>
<style src="./App.css" />
