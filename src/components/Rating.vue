<template>
  <div class="rating">
    <span v-for="star in maxStars" :key="star">
      <i class="fa fa-star" :class="star <= rating && 'is-checked'"></i> 
    </span>
  </div>
</template>

<script>

export default {
  name: 'Rating',
  data: function() {
    return {
      maxStars: 5
    }
  },
  props: {
    rating: String,
  }
}
</script>

<style scoped>
.fa-star {
  margin: 0 6px;
  color: rgba(255,255,255,0.24);
}

.fa-star.is-checked {
  color: #E7CD22;
}
</style>
