
<template>
  <div>
    <div class="columns is-gapless is-mobile rowgapless">
      <div class="column">
        <box>
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column is-gapless">
        <box>
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box>
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box>
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box>
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box>
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>

      <div class="column">
        <box class="is-fullwidth is-fullheight">
          <pixel :selectedProp="selectedProp" />
        </box>
      </div>
    </div>
  </div>
</template>
<script>
import pixel from "./pixel";

export default {
  name: "row",
  props: ["selectedProp"],
  components: {
    pixel
  },

  data() {
    return {
      selected: 5
    };
  }
};
</script>


<style>
</style>
