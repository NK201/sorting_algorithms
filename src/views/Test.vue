<template>
  <div class="bubblesort">
    <h1>Test</h1>

    <h3>TESTTESTTEST</h3>

    <button @click="fillData()">Randomize Data</button>
    <Test_visualisation></Test_visualisation>
  </div>
</template>


  <script>
/* eslint-disable */
import Test_visualisation from "../components/Test_visualisation.vue";

export default {
  name: "test",
  components: {
    Test_visualisation
  },
  methods: {
    fillData() {
      this.datacollection = {};
    }
  }
};
</script>

<style scoped>
</style>
