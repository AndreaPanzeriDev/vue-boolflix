<template>
  <div>
    <h2 class="text-white">Serie Tv</h2>
    <div id="cards">
      <CardComp
        v-for="(elem, index) in arraySeriesFull"
        :key="index"
        :singleItem="elem"
      />
    </div>
  </div>
</template>

<script>
import CardComp from "./CardComp.vue";

export default {
  name: "SerieList",
  components: {
    CardComp,
  },
  props: {
    arraySeriesFull: Array,
  },
};
</script>

<style scoped>

</style>