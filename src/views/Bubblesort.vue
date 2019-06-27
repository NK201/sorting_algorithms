<template>
  <div class="bubblesort">
    <h1>Bubblesort</h1>

    <h3>Erster Test mit Visualisierungen</h3>

    <button @click="randomizeData()">Randomize Data</button>
    <Bubblesort_visualisation></Bubblesort_visualisation>
  </div>
</template>


  <script>
/* eslint-disable */
import Bubblesort_visualisation from "../components/Bubblesort_visualisation.vue";

export default {
  name: "bubblesort",
  components: {
    Bubblesort_visualisation
  },
  methods: {
    randomizeData() {
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
            data: [
              1,
              22,
              8,
              4,
              5,
              6,
              17,
              4,
              9,
              10,
              17,
              12,
              3,
              5,
              15,
              16,
              17,
              18,
              19,
              20,
              12,
              22,
              23,
              15,
              19
            ]
          }
        ]
      };
    }
  }
};
</script>

<style scoped>
</style>
