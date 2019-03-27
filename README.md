# vue-fade-images

Lightweight, easy to configure component for displaying a sequence of alternating image files.

## Usage

After installation the module can be used as follows:
```
<template>
  <div>
    <fade-images :delay="2000" :width="400" :height="400"
                :images="images" />
  </div>
</template>

<script>
import FadeImages from '/vue-fade-images'

export default {
  data () {
    return {
      images: [
        {src: require("@/assets/img_1.png") },
        {src: require("@/assets/img_2.png") },
        {src: require("@/assets/img_3.png") }
      ]
    }
  },
  components: {
    FadeImages
  }
}
</script>
```

## Built With

* [vue.js](https://vuejs.org/)
