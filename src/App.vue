<template>
  <div>
    <h1>COVID-19 Casos Confirmados por País</h1>
    <canvas ref="chart"></canvas>
  </div>
</template>

<script>
import axios from 'axios';
import Chart from 'chart.js/auto';

export default {
  data() {
    return {
      countriesData: [],
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      try {
        const response = await axios.get('https://covid19-brazil-api.now.sh/api/report/v1/countries');
        this.countriesData = response.data.data;
        this.createChart();
      } catch (error) {
        console.error('Erro ao buscar dados da API:', error);
      }
    },
    createChart() {
      const ctx = this.$refs.chart.getContext('2d');
      const labels = this.countriesData.map(country => country.country);
      const data = this.countriesData.map(country => country.cases);

      new Chart(ctx, {
        type: 'bar',
        data: {
          labels,
          datasets: [{
            label: 'Casos Confirmados',
            data,
            backgroundColor: 'rgba(75, 192, 192, 0.2)',
            borderColor: 'rgba(75, 192, 192, 1)',
            borderWidth: 1,
          }],
        },
        options: {
          scales: {
            y: {
              beginAtZero: true,
            },
          },
        },
      });
    },
  },
};
</script>

<style scoped>
.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

.chart-container {
  position: relative;
  height: 400px;
}

canvas {
  width: 100% !important;
  height: 100% !important;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(176, 237, 20, 0.1);
}   
</style>
