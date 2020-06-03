<template>
  <div id="app">
    <IsoDrawApp />
  </div>
</template>

<script>
import IsoDrawApp from "./components/IsoDrawApp.vue";

export default {
  name: "app",
  components: {
    IsoDrawApp
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
