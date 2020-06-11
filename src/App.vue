<template>
  <div id="app">
    <header-banner />
  </div>
</template>

<script>
import HeaderBanner from './components/HeaderBanner.vue'

export default {
  name: 'App',
  components: {
    HeaderBanner
  }
}
</script>

<style>
#app {
  font-family: Futura, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
