<script setup>
import ButtonLink from '../components/ButtonLink.vue';
</script>

<template>
  <header>
    <h1>gitmoji Stats</h1>
    <p id="description">Display the gitmoji frequency of your repositories</p>

    <nav class="nav-buttons">
      <ButtonLink url="https://gitmoji.dev/" text="Gitmoji"/>
      <ButtonLink url="https://github.com/Sigmanificient/Gitmoji-stats" text="Repository"/>
    </nav>
  </header>
</template>

<style scoped>
header {
  background-color: var(--primary);
  padding: 3em 2em;
  text-align: center;
}

h1 {
  margin-block: 0;
  font-size: 5em;
}

p#description {
  font-size: 1.5em;
  font-weight: bold;
}

.nav-buttons {
  display: flex;
  justify-content: center;
  gap: 2em;
}
</style>