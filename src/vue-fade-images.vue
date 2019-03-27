<template>
  <div id="slider_wrap">
    <transition name="crossfade">
        <img :key="current_img" :width="x" :height="y"  :src="getImgPath(current_img)" >
    </transition>
  </div>
</template>

<script>
export default {
  name: "VueFadeImages",
  props: {
    images: Array,
    width: {
      type: Number,
      default: 200
    },
    height: {
      type: Number,
      default: 200
    },
    delay: {
      type: Number,
      default: 1000
    }
  },
  data () {
    return {
      current_img: this.images[0],
      time: this.delay,
      x: this.width,
      y: this.height,
      img_idx: 0
    }
  },
  mounted () {
    this.$options.interval = setInterval(this.changePicture, this.time);
  },
  methods: {
    getImgPath (imgName) {
        return imgName ? require(`../assets/${imgName}`) : ''
    },
    changePicture () {
        this.img_idx++;
        this.current_img = this.images[this.img_idx % this.images.length];
    }
  },
  beforeDestroy () {
    clearInterval(this.$options.interval);
  }
};
</script>

<style scoped>
#slider_wrap img {
  position: absolute;
}
.crossfade-enter-active, .crossfade-leave-active {
  transition: opacity 1s linear;
}
.crossfade-enter, .crossfade-leave-active {
  opacity: 0;
}
</style>
