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
      <IsoDrawGrid :radiusRatio="ratio" :grabber="grabber"></IsoDrawGrid>
    </section>
  </div>
</template>

<script>
import IsoDrawGrid from "./IsoDrawGrid.vue";

export default {
  name: "IsoDrawApp",
  data() {
    return {
      ratio: 30,
      grabber: true,
      isActive: true,

      imageData: ""
    };
  },

  components: {
    IsoDrawGrid
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
