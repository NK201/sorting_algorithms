<template>
  <div class="test">
    <h1>Test</h1>
    <h3>TEST TEST TEST</h3>

    <button @click="randomize()">Test</button>
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
            backgroundColor: "#f87979",
            data: [this.getRandomInt(), this.getRandomInt()]
          },
          {
            label: "Data One",
            backgroundColor: "#f87979",
            data: [this.getRandomInt(), this.getRandomInt()]
          }
        ]
      };
    },
    getRandomInt() {
      return Math.floor(Math.random() * (50 - 5 + 1)) + 5;
    }
  }
};
</script>

<style scoped>
/* .test {
  max-width: 600px;
  margin: 150px auto;
} */
</style>
