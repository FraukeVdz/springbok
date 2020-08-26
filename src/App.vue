<template>
  <div id="app">
    <Banner v-bind:rating="rating" v-bind:percentage="percentage" />
    <div class="form-item">
      <label for="rating">Rating</label>
      <input type="number" id="rating" name="rating" v-model="rating" min="0" max="5">
    </div>
    <div class="form-item">
      <label for="percentage">Percentage</label>
      <input type="number" id="percentage" name="percentage" v-model="percentage" min="0" max="100">
    </div>
  </div>
</template>

<script>
import Banner from './components/Banner.vue';

export default {
  name: 'App',
  components: {
    Banner
  },
  data: function () {
    return {
      rating: "4",
      percentage: "84"
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
