<script setup>
function searchGithubRepo() {
  let input = document.getElementById('search-github-repo')

  console.log(input.value);
}
</script>

<template>
  <div class="wrap">
    <div class="form">
      <input
          id="search-github-repo"
          type="text"
          placeholder="Search your Github repository..."
      >
      <button class="btn" type="button" @click="searchGithubRepo()">Search</button>
    </div>
    <div class="graph">

    </div>
  </div>
</template>

<style scoped>
  .wrap {
    padding: 4em;
    max-width: 1100px;
    margin: 0 auto;
  }

  .graph {
    margin-top: 2em;
    height: 600px;
    width: 100%;
    background-color: var(--cardBackground);
    border-radius: 4px;
  }

  .form {
    display: flex;
    justify-content: center;
    flex-flow: row wrap;
    gap: 1em;
  }

  .form input {
    color: var(--textInSecondary);
    background-color: var(--cardBackground);
    border-radius: 4px;
    border: 0;
    flex: 1 1;
    font-size: 1rem;
    padding: 1rem;
    margin-right: 1rem;
  }

  .btn {
    border: 0;
  }
</style>