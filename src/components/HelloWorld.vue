<template>
  <div>
    <section>
      <div class="columns is-mobile">
        <div class="column is-mobile">
          <b-numberinput controls-position="compact" v-model="ratio" step="5" min="15" max="80"></b-numberinput>
        </div>
        <div class="column is-mobile">
          <b-switch v-model="grabber">Pin Canvas</b-switch>
        </div>
      </div>
      <IsoGrid :radiusRatio="ratio" :grabber="grabber"></IsoGrid>
    </section>
  </div>
</template>

<script>
import IsoGrid from "./IsoGrid.vue";

export default {
  name: "HelloWorld",
  data() {
    return {
      ratio: 30,
      grabber: true,
      isActive: true,
      isImageModalActive: false,
      ispicPixelAppActive: false,
      isCardModalActive: false,
      imageData: ""
    };
  },

  methods: {
    toggleGrabber() {
      this.grabber = !this.grabber;
    }
  },

  components: {
    IsoGrid
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
