<template>
  <div id="picPixelApp">
    <box class="is-fullwidth">
      <palbar v-on:suckSwatch="getSwatch" class="marge" />
      <mycanvas :selectedProp="selectedSwatch" />
    </box>
  </div>
</template>

<script>
import palbar from "./palbar.vue";
import mycanvas from "./myCanvas.vue";

export default {
  name: "picPixelApp",
  data() {
    return {
      selectedSwatch: 7
    };
  },
  methods: {
    getSwatch(value) {
      this.selectedSwatch = value;
    }
  },
  components: {
    palbar,
    mycanvas
  }
};
</script>

<style scoped>
.marge {
  margin-bottom: -4px;
}
</style>