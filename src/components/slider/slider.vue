<template>
  <div class="container">
    <!-- <div class="slider__wrapper" ref="wrap">
      <div
        class="slider__heros"
        :style="{ 'margin-left': '-' + 100 * count + '%' }"
      >
        <vSliderItem :slider_item="item" v-for="item in slider" :key="item" />
      </div>
    </div>
    <div class="slider__button">
      <button class="slider__prev">prev</button>
      <button class="slider__next">next</button>
    </div> -->
    <div class="slider">
      <div
        class="slider-line"
        :style="{ 'margin-left': '-' + 100 * count + '%' }"
      >
        <vSliderItem :slider_item="item" v-for="item in slider" :key="item" />
      </div>
    </div>

    <button class="button slider-prev" @click="prev">Prev</button>
    <button class="button slider-next" @click="next">Next</button>
  </div>
</template>
<script>
import vSliderItem from "./slider-item.vue";
export default {
  name: "slider",
  components: { vSliderItem },
  computed: {},
  methods: {
    prev() {
      this.count--;
      this.rollSlider();
    },
    next() {
      if (this.count >= this.slider.length - 1) {
        this.count = 0;
      } else this.count++;
      this.rollSlider();
    },
  },
  mounted() {
    const images = document.querySelectorAll(".slider .slider-line img");
    const sliderLine = document.querySelector(".slider .slider-line");
    let count = 0;
    let width;

    function init() {
      console.log("resize");
      width = document.querySelector(".slider").offsetWidth;
      sliderLine.style.width = width * images.length + "px";
      images.forEach((item) => {
        item.style.width = width + "px";
        item.style.height = "auto";
      });
      rollSlider();
    }

    init();
    window.addEventListener("resize", init);
    function rollSlider() {
      sliderLine.style.transform = "translate(-" + count * width + "px)";
    }
  },
  data() {
    return {
      count: 0,
    };
  },
  props: {
    slider: {
      type: [String, Array],
      default: null,
    },
  },
};
</script>

<style lang="scss">
.container {
  max-width: 1200px;
  margin: 30px auto;
  background: #f1f1f1;
  padding: 30px;
}

.slider {
  border: 2px solid black;
  /* width: 100%; */
  max-width: 80%;
  /* height: 300px; */
  margin: 20px auto;
  overflow: hidden;
}

.slider-line {
  width: 1024px;
  display: flex;
  background: orange;
  position: relative;
  left: 0;
  transition: all ease 1s;
}
// .slider {
//   &__wrapper {
//     display: flex;
//     width: 100%;
//     height: 300px;
//     overflow: hidden;
//   }
//   &__heros {
//     display: flex;
//     width: 1024px;
//   }
//   &__button {
//     @extend .slider__heros;
//     justify-content: center;
//     height: 100px;
//   }
//   &__btn {
//     margin: 20px;
//     padding: 20px;
//   }
// }
</style>
