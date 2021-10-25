<template>
  <div id="app">
    <VueSlickCarousel
      v-bind="settings"
      v-if="slides.length"
      ref="carousel"
      class="carousel"
    >
      <div class="work" v-for="img in slides" :key="img">
        <img :src="img" />
      </div>
    </VueSlickCarousel>
  </div>
</template>

<script>
/* eslint-disable no-unused-vars */
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
  name: "WorksCarousel",
  components: { VueSlickCarousel },
  data() {
    return {
      slides: [
        "https://loremflickr.com/320/240?random=1",
        "https://loremflickr.com/320/240?random=2",
        "https://loremflickr.com/480/480?random=3",
        "https://loremflickr.com/320/240?random=4",
        "https://loremflickr.com/320/240?random=5"
      ],
      currentSlide: 0,
      settings: {
        autoplay: true,
        adaptiveHeight: true,
        arrows: true,
        slidesToShow: 3,
        slidesToScroll: 1,
        infinite: true,
        variableWidth: true,
        draggable: true
      }
    };
  },
  watch: {
    currentSlide(newValue, oldValue) {
      this.$refs.carousel.goTo(newValue);
    }
  },
  methods: {
    updateIndexOnClick(slideIndex) {
      this.currentSlide = slideIndex;
    },
    updateIndexOnDrag(oldSlideIndex, newSlideIndex) {
      this.currentSlide = newSlideIndex;
    }
  }
};
</script>

<style scoped>
.carousel {
  width: 100%;
  padding: 10px;
}

img {
  user-select: none;
  -webkit-user-drag: none;
}

.slick-slide {
   max-height:200px;
}

.slick-slide img {
   max-height:200px;
   margin: 10px;
}
</style>
