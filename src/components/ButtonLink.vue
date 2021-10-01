<script setup>
defineProps({
  url: String,
  text: String
})
</script>

<template>
  <a class="btn" href="{{ url }}">{{ text }}</a>
</template>

<style scoped>
.btn {
  padding: 1em 2em;
  background: var(--secondary);
  color: var(--textInSecondary);
  box-shadow: 0 4px var(--secondaryShadow);
  border-radius: 4px;
  text-decoration: none;
  font-weight: 700;
  cursor: pointer;
  position: relative;
  user-select: none;
}

.btn:hover {
  top: 2px;
  box-shadow: 0 2px var(--secondaryShadow);
  -webkit-animation: none;
  animation: none;
}

.btn:active {
  box-shadow: 0 0 var(--secondary);
  top: 4px;
}
</style>