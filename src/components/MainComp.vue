<template>
  <div>
    <FilmList />
    <SerieList />
  </div>
</template>

<script>
import FilmList from "./film/FilmList.vue";
import SerieList from "./tvseries/SerieList.vue";

export default {
  name: "MainComp",
  components: {
    FilmList,
    SerieList,
  },
};
</script>

<style>
</style>