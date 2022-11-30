<template>
  <div>
    <h2>Films</h2>
    <div id="cards">
      <CardComp
        v-for="(elem, index) in arrayFilmFull"
        :key="index"
        :singleItem="elem"
      />
    </div>
  </div>
</template>

<script>
import CardComp from "./CardComp.vue";

export default {
  name: "FilmList",
  components: {
    CardComp,
  },
  props: {
    arrayFilmFull: Array,
  },
};
</script>

<style>
#cards {
  width: 95%;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
}
</style>