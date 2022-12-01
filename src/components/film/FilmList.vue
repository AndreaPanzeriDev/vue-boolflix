<template>
  <div>
    <h2 class="text-white">Films</h2>
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

<style scoped>
#cards {
  width: 95%;
  margin: auto;
  overflow-y: hidden;
  overflow-x: scroll;
  white-space: nowrap;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}

#cards:hover{
  -ms-overflow-style: auto; /* IE and Edge */
  scrollbar-width: auto; /* Firefox */
}
/* Hide scrollbar for Chrome, Safari and Opera */
#cards::-webkit-scrollbar {
  display: none;
}
</style>