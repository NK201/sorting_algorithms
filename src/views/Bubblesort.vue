<template>
  <div class="bubblesort">
    <h1>Bubblesort</h1>

    <h3>Erster Test mit Visualisierungen</h3>

    <div class="chart">
      <Bubblesort_visualisation></Bubblesort_visualisation>
    </div>
  </div>
</template>


  <script>
/* eslint-disable */
import Bubblesort_visualisation from "../components/Bubblesort_visualisation.vue";

export default {
  name: "bubblesort",
  components: {
    Bubblesort_visualisation
  }
};
</script>

<style scoped>
.chart {
  /* TODO */
}
</style>
