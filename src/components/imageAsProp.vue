<template>
  <div id="imageAsProp">
    <h1>Inside Image As Prop!</h1>
    <img class="preview" :src="imageData.sourcc" />
    <v-stage ref="stage" :config="configKonva">
      <v-layer ref="layer">
        <p>attempt to insert here</p>
        <img class="directPropImg" :src="imageData.sourcc" />
        <p>---snip</p>
        <v-rect
          :config="{
          x: 20,
          y: 250,
          width: 100,
          height: 100,
          
          shadowBlur: 10,
          fillPatternImage: brick,
          fillPatternOffset: { x: 200, y: 200 },
          fillPatternScaleX: 1,
          fillPatternScaley: 1
        }"
        />

        <v-rect
          :config="{
          x: 220,
          y: 250,
          width: 100,
          height: 100,
          
          shadowBlur: 10,
          fillPatternImage: imageData.sourcc,
         
          fillPatternScaleX: 1,
          fillPatternScaley: 1
        }"
        />
      </v-layer>
    </v-stage>
  </div>
</template>

<script>
const width = window.innerWidth * 1.5;
const height = window.innerHeight * 1.5;
export default {
  name: "imageAsProp",
  props: ["sharedImage"],

  computed: {
    currentSharedImage() {
      if (this.sharedImage.length > 0) {
        return { sourcc: this.sharedImage };
      } else {
        // return "../assets/brick.png";
        return { sourcc: require("../assets/" + 1 + ".jpg") };
      }
    },
    imageData() {
      return { sourcc: this.sharedImage };
    }
  },
  data() {
    return {
      configKonva: {
        width: width,
        height: height,
        strokeWidth: 5
      }
    };
  },

  created() {
    const brick = new window.Image();
    brick.src = require("../assets/brick.png");
    brick.onload = () => {
      // set image only when it is loaded
      this.brick = brick;
    };

    let sharedImageObj = new window.Image();
    sharedImageObj.onload = () => {
      // set image only when it is loaded
      this.sharedImageObj = sharedImageObj;
    };
    sharedImageObj.src = this.sharedImage;
  }
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>