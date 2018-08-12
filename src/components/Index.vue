<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <canvas id="planet-chart"></canvas>
  </div>
</template>

<script>
import Chart from 'chart.js'
import planetChartData from '@/assets/data/chart-data.js'
export default {
  name: 'Index',
  data () {
    return {
      msg: 'Welcome to Economic statistics',
      planetChartData
    }
  },
  mounted () {
    this.createChart('planet-chart', this.planetChartData)
  },
  methods: {
    createChart (chartId, chartData) {
      const ctx = document.getElementById(chartId)
      new Chart(ctx, {
        type: chartData.type,
        data: chartData.data,
        options: chartData.options
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
