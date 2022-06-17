<script setup>
function searchGithubRepo()
{
  let input = document.getElementById('search-github-repo')
  let commits = getAllCommits(input.value)
  console.log(commits)

  for (let i = 0; i < commits.length; i++) {
    let commit_name = commits[i];
    let moji = mapCommitToGitmoji(commit_name)
    console.log(moji);
  }
}

function getAllCommits(repo) {
  let commits = [];
  const API_URL = `https://api.github.com/repos/${repo}/commits`;

  fetch(API_URL)
    .then(response => response.json())
    .then(data => {
      data.forEach(commit => {
        commits.push(commit.commit.message);
      });
    })
    .catch(error => console.error(error))

  return commits;
}

function mapCommitToGitmoji(commit_name) {
  const GITMOJI_MAP = {
    'art': '🎨',
    'zap': '⚡️',
    'fire': '🔥',
    'bug': '🐛',
    // ...
  }

  for (let key in GITMOJI_MAP) {
    console.log(key);
    if (commit_name.includes(`${key}`) || commit_name.includes(`${GITMOJI_MAP[key]}`)) {
      return GITMOJI_MAP[key]
    }
  }

  return 'unknown'
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
      <canvas id="graph" width="400" height="400"></canvas>
    </div>
  </div>
</template>

<style scoped>
.wrap {
  padding: 4em;
  max-width: 1100px;
  margin: 0 auto;
}

#graph {
  padding: 2em;
  margin-top: 3em;
  height: 600px;
  width: calc(100% - 4em);
  background-color: var(--cardBackground);
  border-radius: 4px;
}

.form {
  display: flex;
  justify-content: center;
  flex-flow: row wrap;
  gap: 2em;
}

.form input {
  color: var(--textInSecondary);
  background-color: var(--cardBackground);
  border-radius: 4px;
  border: 0;
  flex: 1 1;
  font-size: 1rem;
  padding: 1rem;
}

.btn {
  border: 0;
}
</style>