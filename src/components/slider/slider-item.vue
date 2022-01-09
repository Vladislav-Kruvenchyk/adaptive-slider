<template>
  <div>
    <img :src="require('../../assets/images/' + this.slider_item)" alt="" />
  </div>
</template>

<script>
export default {
  name: "slider-item",
  props: {
    slider_item: {
      type: [String, Array],
      default: null,
    },
  },
};
</script>

<style lang="scss">
// img {
//   width: 900px;
//   height: 300px;
// }
</style>
