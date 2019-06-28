<template>
  <div class="bogosort">
    <h1>Bogosort aka Monkeysort aka Stupidsort</h1>
    <h3>Die Elemente werden in einem Array so lange gemischt bis sie zufällig sortiert sind.</h3>

    <button @click="fillRandomData()">Randomize Data</button>
    <button @click="shuffleData()">Shuffle Data</button>
    <button @click="shuffleUntilSorted()">Sort it</button>

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
      sorted: false,
      arrSize: 4,
      color: "#121212"
    };
  },
  mounted() {
    this.fillRandomData();
  },
  watch: {
    // data: function() {
    //   this._chart.destroy();
    //   //this.renderChart(this.data, this.options);
    //   this.renderBarChart();
  },
  methods: {
    // TODO somehow make this wait 1 sec between each shuffle
    shuffleUntilSorted() {
      this.shuffleData();
      if (!this.sorted) {
        // recursive call after 1 secs

        setTimeout(this.shuffleUntilSorted, 1000);
      }
    },
    fillRandomData() {
      this.datacollection = {
        labels: ["1", "2", "3", "4", "5"],
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
    shuffleData() {
      var arr = this.datacollection.datasets[0].data;
      // shuffle the datacollection.datasets[0].data array == arr
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }

      this.datacollection = {
        labels: ["1", "2", "3", "4", "5"],
        datasets: [
          {
            label: "Bogosort",
            backgroundColor: this.datacollection.datasets[0].backgroundColor,
            data: arr
          }
        ]
      };
      this.checkIfSorted();

      console.log(this.datacollection.datasets[0].data);

      // update the chart
      //this.datacollection.update();
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

      // set current color
      this.color = color;

      return color;
    },
    getRandomArray() {
      var arr = [];
      for (var i = 0; i < this.arrSize; i++) {
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
