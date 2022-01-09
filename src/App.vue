<template>
  <div id="app">
    <!-- <div class="container">
      <div class="slider">
        <div class="slider-line">
          <img src="./assets/images/111.jpg" alt="" />
          <img src="./assets/images/112.jpg" alt="" />
          <img src="./assets/images/113.jpg" alt="" />
          <img src="./assets/images/114.jpg" alt="" />
          <img src="./assets/images/115.jpg" alt="" />
        </div>
      </div>

      <button class="button slider-prev">Prev</button>
      <button class="button slider-next">Next</button>
    </div> -->
    <vSlider :slider="images" />
  </div>
</template>

<script>
import vSlider from "./components/slider/slider.vue";
export default {
  name: "App",
  components: {
    vSlider,
  },
  data() {
    return {
      images: ["111.jpg", "112.jpg", "113.jpg", "114.jpg", "115.jpg"],
    };
  },
  mounted() {
    // const images = document.querySelectorAll(".slider .slider-line img");
    // const sliderLine = document.querySelector(".slider .slider-line");
    // let count = 0;
    // let width;
    // function init() {
    //   console.log("resize");
    //   width = document.querySelector(".slider").offsetWidth;
    //   sliderLine.style.width = width * images.length + "px";
    //   images.forEach((item) => {
    //     item.style.width = width + "px";
    //     item.style.height = "auto";
    //   });
    //   rollSlider();
    // }
    // init();
    // window.addEventListener("resize", init);
    // document
    //   .querySelector(".slider-next")
    //   .addEventListener("click", function () {
    //     count++;
    //     if (count >= images.length) {
    //       count = 0;
    //     }
    //     rollSlider();
    //   });
    // document
    //   .querySelector(".slider-prev")
    //   .addEventListener("click", function () {
    //     count--;
    //     if (count < 0) {
    //       count = images.length - 1;
    //     }
    //     rollSlider();
    //   });
    // function rollSlider() {
    //   sliderLine.style.transform = "translate(-" + count * width + "px)";
    // }
  },
};
</script>

<style lang="scss">
// #app {
//   display: flex;
//   height: 100vh;
//   justify-content: center;
//   align-items: center;
// }

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
</style>
