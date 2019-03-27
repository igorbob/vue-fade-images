# vue-fade-images

Lightweight, easy to configure component for displaying a sequence of alternating image files.

## Install

Install using npm
```
npm install vue-fade-images
```


ES6/commonjs import
```
// ES6
import {FadeImages} from 'vue-fade-images';

// commonjs
var Swipe = require("vue-fade-images").fadeImages;
```

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
## Options

| Option  | Description |
| ------------- | ------------- |
| delay  | Number (default: 1000) in milliseconds |
| width  | Number (default: 200) in px |
| height | Number (default: 200) in px |
| images | Array , array of image sources |


## Built With

* [vue.js](https://vuejs.org/)
