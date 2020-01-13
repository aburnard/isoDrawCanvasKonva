<template>
  <div>
    <box class="is-fullwidth is-fullheight">
      <img @click="setSwatch(selectedProp)" :src="getImgUrl.sourcc" />
    </box>
  </div>
</template>

<script>
export default {
  name: "pixel",

  data() {
    return {
      swatch: 9
    };
  },

  props: ["selectedProp"],

  computed: {
    getImgUrl() {
      return { sourcc: require("../assets/" + this.swatch + ".jpg") };
    }
  },

  methods: {
    setSwatch(swindex) {
      this.swatch = swindex;
    }
  }
};
</script>


