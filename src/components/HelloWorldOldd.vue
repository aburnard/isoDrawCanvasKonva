<template>
  <div>
    <h2>Helloworld with simplified imageasprop</h2>

    <section>
      <div class="image-preview" v-if="imageData.length > 0">
        <p>inside helloworld</p>
        <img class="preview" :src="imageData" />
      </div>
      <imageLoad v-on:fileImage="fileImage"></imageLoad>
      <imageAsProp :sharedImage="imageData"></imageAsProp>
    </section>
  </div>
</template>

<script>
import imageLoad from "./imageLoad.vue";
import imageAsProp from "./imageAsProp.vue";

export default {
  name: "HelloWorld",
  data() {
    return {
      isActive: true,
      isImageModalActive: false,
      ispicPixelAppActive: false,
      isCardModalActive: false,
      imageData: ""
    };
  },

  components: {
    imageLoad,
    imageAsProp
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
