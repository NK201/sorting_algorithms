<template>
  <div class="bogosort">
    <h1>Bogosort aka Monkeysort aka Stupidsort</h1>
    <h3>Die Elemente werden in einem Array so lange gemischt bis sie zufällig sortiert sind.</h3>

    <button @click="randomize()">Randomize Data</button>

    <div class="sorted">
      <br>
      Sortiert == {{ sorted }}
    </div>

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
      datacollection: null,
      sorted: false
    };
  },
  mounted() {
    this.randomize();
  },
  methods: {
    randomize() {
      this.datacollection = {
        labels: ["1", "2", "3"],
        datasets: [
          {
            label: "Bogosort",
            backgroundColor: this.getRandomColor(),
            data: this.getRandomArray()
          }
        ]
      };
      this.checkIfSorted();
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
    },
    getRandomArray() {
      var arr = [];
      for (var i = 0; i < 3; i++) {
        var random = Math.floor(Math.random() * 100);
        arr.push(random);
      }
      console.log(arr);
      return arr;
    },
    checkIfSorted() {
      // check if datacollection.data is sorted

      var arrlength = this.datacollection.datasets[0].data.length;
      var sorted = false;
      for (var i = 0; i < arrlength; i++) {
        if (
          this.datacollection.datasets[0].data[i] >
          this.datacollection.datasets[0].data[i + 1]
        ) {
          sorted = false;
          break;
        } else {
          sorted = true;
        }
      }

      this.sorted = sorted;
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
