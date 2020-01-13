<template>
  <div>
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />

    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />

    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
    <row :selectedProp="selectedProp" class="marge" />
  </div>
</template>

<script>
import row from "./row.vue";
export default {
  name: "mycanvas",
  components: {
    row
  },
  props: ["selectedProp"]
};
</script>

<style scoped>
.marge {
  margin-bottom: -7px;
}
</style>