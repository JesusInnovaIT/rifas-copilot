<script setup lang="ts">
import NuevaRifa from './components/NuevaRifa.vue'
</script>

<template>
  <div id="app">
    <NuevaRifa />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  background-color: #f5f5f5;
  min-height: 100vh;
}

#app {
  min-height: 100vh;
  padding: 2rem 0;
}
</style>
