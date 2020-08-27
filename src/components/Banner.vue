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
    position: relative;
    margin: 50px 0;
    background: radial-gradient(circle, #07354A 0%, #031824 100%);
    color: #FFF;
    text-align: center;
  }

  .banner::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: .32;
    background: url('../assets/background.jpg') center center / cover no-repeat;
  }

  .banner--right {
    padding-bottom: 80px;
    overflow: hidden;
  }

  .banner--right::after {
    top: inherit;
    bottom: -160px;
    opacity: 1;
    background: url('../assets/tyre.png') center bottom / 250px auto no-repeat;
  }

  .banner__container {
    position: relative;
    padding: 30px 22px;
    z-index: 1;
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

  @media only screen and (min-width: 768px) {
    .banner {
      display: flex;
      justify-content: center;
      text-align: center;
    }

    .banner--right {
      justify-content: flex-end;
      text-align: right;
      padding: 0;
    }

    .banner--right::after {
      top: 0;
      bottom: inherit;
      background-position: -120px -100px;
      background-size: 350px auto;
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
