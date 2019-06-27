
<template>
  <chart :chart-data="datacollection"></chart>
</template>


<script>
import Chart from "./../BarChart.vue";
export default {
  components: {
    Chart
  },
  data() {
    return {
      datacollection: null
    };
  },
  created() {
    this.fillData();
  },
  mounted() {
    this.fillData();
    // this.renderChart(this.chartData, this.options);
  },
  methods: {
    fillData() {
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
            label: "Bubblesort-Algorithmus",
            backgroundColor: "#999",
            data: [
              1,
              2,
              8,
              4,
              5,
              6,
              7,
              8,
              9,
              10,
              11,
              12,
              13,
              5,
              15,
              16,
              17,
              18,
              19,
              20,
              21,
              22,
              23,
              24,
              25
            ]
          }
        ]
      };
    }
  }
};
</script>
    <style>
</style>