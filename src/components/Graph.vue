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
    <canvas id="graph" width="400" height="400"></canvas>
  </div>
</template>
<script>

import {Chart, LinearScale, registerables} from "chart.js";

window.onload = () => {
  Chart.register(...registerables);

  let ctx = document.getElementById('graph').getContext('2d');
  let myChart = new Chart(ctx, {
    type: 'bar',
    data: {
      labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
      datasets: [{
        label: '# of Votes',
        data: [12, 19, 3, 5, 2, 3],
        backgroundColor: [
          'rgba(255, 99, 132, 0.2)',
          'rgba(54, 162, 235, 0.2)',
          'rgba(255, 206, 86, 0.2)',
          'rgba(75, 192, 192, 0.2)',
          'rgba(153, 102, 255, 0.2)',
          'rgba(255, 159, 64, 0.2)'
        ],
        borderColor: [
          'rgba(255, 99, 132, 1)',
          'rgba(54, 162, 235, 1)',
          'rgba(255, 206, 86, 1)',
          'rgba(75, 192, 192, 1)',
          'rgba(153, 102, 255, 1)',
          'rgba(255, 159, 64, 1)'
        ],
        borderWidth: 1
      }]
    },
    options: {
      scales: {
        y: {
          beginAtZero: true
        }
      }
    }
  });
}
</script>

<style scoped>
.wrap {
  padding: 4em;
  max-width: 1100px;
  margin: 0 auto;
}

#graph {
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