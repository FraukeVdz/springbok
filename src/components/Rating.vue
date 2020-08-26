<template>
  <div class="rating">
    {{ rating }} stars
  </div>
</template>

<script>

export default {
  name: 'Rating',
  props: {
    rating: String,
  }
}
</script>

<style scoped>

</style>
