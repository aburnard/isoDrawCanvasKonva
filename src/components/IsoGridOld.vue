<template>
  <div id="IsoGrid">
    <v-stage ref="stage" :config="configKonva">
      <v-layer ref="layer">
        <v-regular-polygon
          @click="handleClick"
          v-for="item in list"
          :key="item.id"
          :config="{
            x: item.x,
            y: item.y,
           
            id: item.id,
            
            sides:3,
            radius:100,
            fill:item.fill,
            stroke: 'yellow',
            rotation: item.rotation

          }"
        ></v-regular-polygon>
      </v-layer>
    </v-stage>
  </div>
</template>

<script>
const width = window.innerWidth;
const height = window.innerHeight;
export default {
  name: "IsoGrid",
  data() {
    return {
      isActive: true,

      list: [],
      dragItemId: null,
      clickItemId: null,
      configKonva: {
        width: width,
        height: height,
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