<script setup>
import Header from './components/Header.vue';
</script>
<template>
  <Header/>
</template>

<style>
:root {
  --primary: #ffdd67;
  --background: #121212;

  --textInPrimary: #000;
  --textInSecondary: #fff;

  --secondary: #ff5a79;
  --secondaryShadow: #f3002e;
}

body {
  background-color: var(--background);
  margin: 0;
}

#app {
  font-size: clamp(12px, 1vw, 16px);
  font-family: Segoe UI, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--textInPrimary)
}
</style>
