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
      <div class="d-flex text-white">
        <span class="fw-bold text-center">{{ singleItem.title }}</span>
      </div>
      <!--score-->
      <div class="d-flex text-white">
        <span class="fw-bold text-center fs-3 text-success mx-auto"
          >{{ singleItem.vote_average }}/10</span
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComp",
  props: {
    singleItem: Object,
  },
  data(){
    return{
      stars: 0,
    }
  },
  methods:{
    getStars(){
      const score = {{this.singleItem.vote_average}},
      this.stars = Math.ceil(score)
    }
  }
};
</script>

<style scoped>
/***************
      CARD
****************/
.card {
  width: calc(100% / 6 - 5px);
  margin: 2.5px;
  height: auto;
  position: relative;
  transition: transform 1500ms;
  transform-style: preserve-3d;
}

.card:hover {
  transform: rotateY(180deg);
}
.card > .thefront > img {
  max-width: 100%;
  display: block;
}
.card:hover img {
  display: none;
}
/*******************
    THE FRONT
*********************/
.thefront {
  height: 100%;
}
.card:hover .thefront {
  display: none;
}
/*******************
      THE BACK
*********************/

.card:hover .theback {
  display: block;
  background-color: black;
  opacity: 0.8;
}
.theback {
  display: none;
  position: absolute;
  top: 0;
  left: 0;
  overflow-y: scroll;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
  transform: rotateY(180deg);
  height: 100%;
}

/* Hide scrollbar for Chrome, Safari and Opera */
.theback::-webkit-scrollbar {
  display: none;
}
</style>
Footer
