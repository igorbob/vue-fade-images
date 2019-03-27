<template>
  <div id="slider_wrap">
    <transition name="crossfade">
        <img :key="current_img" :width="x" :height="y"  :src="current_src" >
    </transition>
  </div>
</template>

<script>
export default {
  name: "FadeImages",
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
      current_src: this.images[0].src,
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
    changePicture () {
        this.img_idx++;
        this.current_src = this.images[this.img_idx % this.images.length].src;
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
