<template>
  <div class="card">
    <img
      :src="`http://image.tmdb.org/t/p/w342/${singleItem.poster_path}`"
      alt="poster"
    />
  </div>
</template>

<script>
export default {
  name: "CardComp",
  props: {
    singleItem: Object,
  },
};
</script>

<style scoped>
.card {
  height: auto;
  background-color: rgb(116, 115, 115);
  display: flex;
  flex-wrap: wrap;
  width: calc(100% / 8 - 5px);
  margin: 2.5px;

}

.card > img{
  max-width: 100%;
}


</style>