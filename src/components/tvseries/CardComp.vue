<template>
  <div class="card">
    <div class="thefront">
      <img
        :src="`http://image.tmdb.org/t/p/w342/${singleItem.poster_path}`"
        alt="poster"
      />
    </div>
    <div class="theback">
      <div class="content">
        <div>ciao</div>
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
};
</script>

<style scoped>

/***************
      CARD
****************/
.card{
  width: calc(100% / 8 - 5px);
  margin: 2.5px;
  height: auto;
}


/***************
    THE FRONT
****************/

.thefront{
  position: relative;
  visibility: visible;
}

.thefront > img {
  max-width: 100%;  
}

.thefront:hover img{
  visibility: hidden;
}


/***************
    THE BACK
****************/
.theback{
  display: none;
}



</style>