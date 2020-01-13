<template>
  <div id="IsoPicPixels">
    <div id="box">
      <v-stage ref="stage" :config="configKonva">
        <v-layer ref="layer">
          <v-regular-polygon
            @click="handleClick"
            @tap="handleClick"
            v-for="item in list"
            :key="item.id"
            :config="{
            x: item.x * recieveRadiusRatio.ratio,
            y: item.y * recieveRadiusRatio.ratio,
            
            id: item.id,
            
            sides:3,
            radius:100 * recieveRadiusRatio.ratio,
            fill:item.fill,
            stroke: 'yellow',
            rotation: item.rotation,
            fillPatternScaleX: .032,
            fillPatternScaley: .032,
            fillPatternX: 0,
            fillPatternY: 0
          }"
          ></v-regular-polygon>
        </v-layer>
      </v-stage>
    </div>
  </div>
</template>

<script>
const width = 3000;
const height = 3000;

export default {
  name: "IsoPicPixels",
  props: "radiusRatio",
  data() {
    return {
      isActive: true,
      yoda: null,
      bricktwo: null,
      brickthree: null,
      list: [],
      dragItemId: null,
      clickItemId: null,
      ratio: 0.3,
      configKonva: {
        width: width,
        height: height,
        draggable: true,
        strokeWidth: 4
      }
    };
  },

  methods: {
    handleClick(e) {
      const clickItemId = e.target.id();
      const item = this.list.find(i => i.id === clickItemId);

      if (item.fill == "blue") {
        item.fill = "red";
      } else if (item.fill == "red") {
        item.fill = "yellow";
      } else if (item.fill == "yellow") {
        item.fill = "blue";
      }
    }
  },

  mounted() {
    //

    //

    for (let hexRow = 0; hexRow < 30; hexRow++) {
      for (let n = 0; n < 30; n++) {
        this.list.push({
          id: Math.round(Math.random() * 100000).toString(),
          x: n * 170 + (hexRow % 2) * 85,

          fill: "blue",

          y: 150 * hexRow
        });
        this.list.push({
          id: Math.round(Math.random() * 100000).toString(),
          rotation: 180,
          x: n * 170 + (hexRow % 2) * 85,
          fill: "blue",

          y: 150 * hexRow + 95
        });
      }
    }
  }
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>