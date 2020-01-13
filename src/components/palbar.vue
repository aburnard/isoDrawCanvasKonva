
<template>
  <div>
    <div class="columns is-gapless is-mobile rowgapless">
      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(1)" src="../assets/1.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(2)" src="../assets/2.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(3)" src="../assets/3.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(4)" src="../assets/4.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(5)" src="../assets/5.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(6)" src="../assets/6.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(7)" src="../assets/7.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(8)" src="../assets/8.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(9)" src="../assets/9.jpg" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <img @click="emitSwatch(10)" src="../assets/10.jpg" />
        </box>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "palbar",
  data() {
    return {
      swatch: 5
    };
  },

  methods: {
    emitSwatch(windex) {
      this.$emit("suckSwatch", windex);
    }
  },

  components: {}
};
</script>

<style>
</style>
