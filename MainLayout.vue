<template>
  <div>
    <h1>Hello from MainLayout!</h1>
    <!-- 其他内容和组件 -->
  </div>
  <div class="home-container">
    <div class="main-area">
      <div class="upper-section">
        <vue-slick-carousel
          :autoplay="true"
          :dots="true"
          :arrows="true"
          :infinite="true"
          :slides-to-show="1"
          :speed="300"
          :autoplay-speed="3000"
          :border-radius="'20px'"
          class="carousel-container"
        >
          <div
            v-for="(slide, index) in slides"
            :key="index"
            class="carousel-slide"
            @click="openModal"
          >
            <img :src="slide.image" :alt="slide.title" class="carousel-image" />
          </div>
        </vue-slick-carousel>
      </div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel';
import 'vue-slick-carousel/dist/vue-slick-carousel.css';
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css';
export default {
  name: "MainLayout",
  components: {
    VueSlickCarousel,
  },
  data() {
    return {
      slides: [
        { image: require("@/assets/img/1.jpeg"), title: "活动1" },
        { image: require("@/assets/img/2.jpeg"), title: "活动2" },
        { image: require("@/assets/img/3.jpeg"), title: "活动3" },
      ],
    };
  },
  methods: {
    openModal() {
      console.log("Open modal");
    },
  },
};
</script>

<style scoped>
.home-container {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  width: 100%;
  min-height: 625px;
  background-color: #f0f0f0;
}

.main-area {
  display: flex;
  flex-direction: column;
  width: 1270px;
  min-height: 602px;
  background-color: #f0f0f0;
}

.upper-section {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 1270px;
  height: 270px;
  background-color: #c0c0c0;
  margin-bottom: 10px;
}

.carousel-container {
  width: 1100px;
  height: 263.2px;
  position: relative;
}

.carousel-slide {
  cursor: pointer;
  position: relative;
  width: 990px;
  height: 236.88px;
  margin: 0 auto;
  border-radius: 20px;
  overflow: hidden;
}

.carousel-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
