<template>
  <div>
    <h2>It was the best of times it was the Blurst of times.</h2>

    <section>
      <img class="preview" :src="imageData" />
      <div class="image-preview" v-if="imageData.length > 0">
        <img class="preview" :src="imageData" />
      </div>
      <imageAsProp :sharedImage="imageData"></imageAsProp>
      <imageLoad v-on:fileImage="fileImage"></imageLoad>
      <column>
        <button class="button is-primary is-medium" @click="isImageModalActive = true">Isometric</button>
      </column>
      <column>
        <button class="button is-primary is-medium" @click="ispicPixelAppActive = true">picPixels</button>
      </column>
      <div class="box">
        <button class="button is-primary is-medium" @click="ispicPixelAppActive = true">picPixels</button>
        <b-slider v-model="ratio"></b-slider>

        <IsoPicPixels :sharedImage="imageData" :radiusRatio="ratio"></IsoPicPixels>
        <IsoGrid :radiusRatio="ratio"></IsoGrid>
      </div>

      <b-modal :active.sync="ispicPixelAppActive">
        <picPixelApp></picPixelApp>
      </b-modal>
    </section>
  </div>
</template>

<script>
import IsoGrid from "./IsoGrid.vue";
import picPixelApp from "./picPixelApp.vue";
import IsoPicPixels from "./IsoPicPixels.vue";
import imageLoad from "./imageLoad.vue";
import imageAsProp from "./imageAsProp.vue";

export default {
  name: "HelloWorld",
  data() {
    return {
      ratio: 30,
      isActive: true,
      isImageModalActive: false,
      ispicPixelAppActive: false,
      isCardModalActive: false,
      imageData: ""
    };
  },

  components: {
    IsoGrid,
    picPixelApp,
    IsoPicPixels,
    imageLoad
  },

  props: ["sharedImage"],
  methods: {
    fileImage(recievedImage) {
      this.imageData = recievedImage;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
