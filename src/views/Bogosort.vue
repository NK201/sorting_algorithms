<template>
  <div class="bogosort">
    <h1>Bogosort aka Monkeysort aka Stupidsort</h1>
    <h3>Die Elemente werden in einem Array so lange gemischt bis sie zufällig sortiert sind.</h3>

    <button @click="randomize()">Randomize Data</button>
    <p>
      Ist sortiert?
      <checkbox/>
    </p>

    <div class="chart">
      <bar-chart :chart-data="datacollection"></bar-chart>
    </div>
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
div.chart {
  max-width: 700px;
  max-height: 700px;
  margin: auto;
}
</style>
