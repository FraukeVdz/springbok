<template>
  <div :class="classObject">
    <div class="banner__container">
      <Rating :rating="rating" />
      <p class="banner__text"><strong class="banner__percentage">{{ percentage }}%</strong> of <strong>some tyre</strong> users recommend this tyre</p>
      <p class="banner__subtext"><strong>Score of {{ rating }} of 5</strong> from 220 reviews</p>
    </div>
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
    type: {
      type: String,
      default: "center"
    }
  },
  computed: {
    classObject: function () {
      return {
        'banner': true,
        'banner--right': this.type && this.type === 'right'
      }
    }
  }
}
</script>

<style scoped>
  .banner {
    margin: 50px 0;
    background: radial-gradient(circle, #07354A 0%, #031824 100%);
    color: #FFF;
    text-align: center;
  }

  .banner__container {
    padding: 30px 22px;
  }

  .banner__text {
    margin: 16px 0 12px;
    font-size: 21px;
    line-height: 1.33;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  .banner__subtext {
    margin: 0;
  }

  @media only screen and (min-width: 480px) {
    .banner {
      display: flex;
      justify-content: center;
      text-align: center;
    }

    .banner--right {
      justify-content: flex-end;
      text-align: right;
    }

    .banner__container {
      max-width: 700px;
      padding: 67px 82px;
    }

    .banner__percentage {
      font-size: 32px;
    }

    .banner__text {
      margin: 12px 0 16px;
      font-size: 28px;
      line-height: 1.36;
      letter-spacing: 6px;
    }
  }
</style>
