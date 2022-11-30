<template>
  <div class="card">
    <div class="thefront">
      <img
        class="poster"
        :src="`http://image.tmdb.org/t/p/w342/${singleItem.poster_path}`"
        alt="poster"
      />
    </div>
    <div class="theback">
      <!--title-->
      <div class="d-flex text-white"><span class="fw-bold">Titolo: </span><span>{{singleItem.title}}</span></div>
      <!--score-->
      <div class="d-flex text-white">
        <span class="fw-bold">Voto:</span>
      </div>
      <!--overview-->
      <div class="d-flex text-white"><span class="fw-bold">Overview:</span>{{singleItem.overview}}<span></span></div>
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
  width: calc(100% / 6 - 5px);
  margin: 2.5px;
  height: 300px;
  position: relative;
  overflow-y: scroll;
  transition: transform 1500ms;
  transform-style: preserve-3d;
}

.card:hover{
  transform: rotateY(180deg);
}

.card > .thefront >img {
  max-width: 100%;
  display: block;
}

.card:hover img {
  display: none;
}

/*******************
    THE FRONT
*********************/

.thefront{
  height: 100%;
}

.card:hover .thefront{
  display: none;
}

/*******************
      THE BACK
*********************/

.theback{
  transform: rotateY(180deg);
  height: auto;
}

.card:hover .theback {
  display: block;
  background-color: black;
  opacity: 0.8;
}

.theback {
  display: none;
}
</style>