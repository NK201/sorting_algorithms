<template>
  <div class="bubblesort">
    <h1>Bubblesort</h1>

    <h3>Erster Test mit Visualisierungen</h3>

    <button @click="randomizeData()">Randomize Data</button>
    <button @click="bubblesortStep()">Bubblesort Step</button>
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
    this.randomizeData();
  },
  methods: {
    bubblesortStep() {
      console.log("test");
    },
    randomizeData() {
      console.log("randomize data - Bubblesort - pressed");
      this.datacollection = {
        labels: [
          "1",
          "2",
          "3",
          "4",
          "5",
          "6",
          "7",
          "8",
          "9",
          "10",
          "11",
          "12",
          "13",
          "14",
          "15",
          "16",
          "17",
          "18",
          "19",
          "20",
          "21",
          "22",
          "23",
          "24",
          "25"
        ],
        datasets: [
          {
            label: "Test-Algorithmus",
            backgroundColor: "#999",
            data: this.getRandomArray()
          }
        ]
      };
    },
    getRandomArray() {
      var arr = [];
      for (var i = 0; i < 25; i++) {
        var random = Math.floor(Math.random() * 100);
        arr.push(random);
      }
      console.log(arr);
      return arr;
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
