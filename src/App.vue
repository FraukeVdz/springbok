<template>
  <div id="app">
    <Banner :rating="rating" :percentage="percentage" type="right" />
    <Banner :rating="rating" :percentage="percentage" />
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
* {
  box-sizing: border-box;
}

html,
body {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0 16px;
  font-family: Helvetica, Arial, sans-serif;
  font-size: 16px;
  line-height: 1.5;
}

@media only screen and (min-width: 768px) {
  html,
  body {
    font-size: 18px;
    line-height: 1.33;
  }
}

label {
  display: block;
  margin-bottom: 5px;
}

input[type="number"] {
  max-width: 268px;
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #979797;
  font: inherit;
}

#app {
  max-width: 1034px;
  margin: 0 auto;
}

.form-item {
  margin-bottom: 15px;
}

</style>
