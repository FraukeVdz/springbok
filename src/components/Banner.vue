<template>
  <div class="banner">
    <Rating :rating="rating" />
    <p><strong>{{ percentage }}%</strong> of <strong>some tyre</strong> users recommend this tyre</p>
    <p><strong>Score of {{ rating }} of 5</strong> from 220 reviews</p>
  </div>
</template>

<script>
import Rating from './Rating.vue';

export default {
  name: 'Banner',
  components: {
    Rating
  },
  props: {
    rating: String,
    percentage: String,
  }
}
</script>

<style scoped>

</style>
