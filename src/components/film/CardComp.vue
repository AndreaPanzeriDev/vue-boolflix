<template>
  <div class="card">
    <img
      class="poster"
      :src="`http://image.tmdb.org/t/p/w342/${singleItem.poster_path}`"
      alt="poster"
    />
    <div class="theback">

    </div>
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
/***************
      CARD
****************/
.card {
  width: calc(100% / 8 - 5px);
  margin: 2.5px;
  height: auto;
  position: relative;
}

.card > img{
  max-width: 100%;
  display: block;
}

.card:hover img{
  display: none;
}

</style>