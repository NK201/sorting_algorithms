<template>
  <div class="test">
    <h1>Random BarChart Test</h1>
    <h3>Test to play with BarCharts. Click to Randomize the Data.</h3>

    <button @click="randomize()">Randomize Data</button>
    <bar-chart :chart-data="datacollection"></bar-chart>
  </div>
</template>


  <script>
import BarChart from "../BarChart.vue";

export default {
  components: {
    BarChart
  },
  data() {
    return {
      datacollection: null
    };
  },
  mounted() {
    this.randomize();
  },
  methods: {
    randomize() {
      this.datacollection = {
        labels: [this.getRandomInt(), this.getRandomInt()],
        datasets: [
          {
            label: "Data One",
            backgroundColor: this.getRandomColor(),
            data: [this.getRandomInt(), this.getRandomInt()]
          },
          {
            label: "Data One",
            backgroundColor: this.getRandomColor(),
            data: [this.getRandomInt(), this.getRandomInt()]
          }
        ]
      };
    },
    getRandomInt() {
      return Math.floor(Math.random() * (50 - 5 + 1)) + 5;
    },
    getRandomColor() {
      var letters = "0123456789ABCDEF";
      var color = "#";
      for (var i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    }
  }
};
</script>

<style scoped>
</style>
