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
      <div class="text-white content">
        <div class="fw-bold text-center">{{ singleItem.title }}</div>
      </div>
      <!--flag-->
      <div>
        <img
          v-if="languages.includes(singleItem.original_language)"
          :src="`../../../public/flags/${singleItem.original_language}.svg`"
          alt="flag"
          class="flag"
        />
        <span v-else>Original Lang: {{singleItem.original_language}}</span>
      </div>

      <!--score-->
      <div class="d-flex text-white">
        <span class="fw-bold text-center fs-3 text-success mx-auto"
          >{{ singleItem.vote_average }}/10</span
        >
      </div>
      <!--score in stars image-->
      <div class="d-flex stars">
        <i
          class="fa-solid fa-star"
          v-for="index in this.stars"
          :key="index"
        ></i>
        <i
          class="fa-solid fa-star text-dark"
          v-for="index in 5 - this.stars"
          :key="index"
        ></i>
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
  data() {
    return {
      stars: Math.ceil(this.singleItem.vote_average / 2),
      languages: ['en', 'it', 'fr', 'es', 'de']
    };
  },
};
</script>

<style scoped>
/***************
      CARD
****************/
.card {
  display: inline-block;
  width: 209px;
  height: 314px;
  transition: transform 1500ms;
  transform-style: preserve-3d;
  position: relative;
}

.card:hover {
  transform: rotateY(180deg);
}
.card > .thefront > img {
  max-width: 100%;
  display: inline-block;
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
  display: inline-block;
  background-color: rgb(137, 137, 137);
  max-height: 100%;
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
  max-width: 209px;
  height: 314px;
  padding: 5px;
}

/* Hide scrollbar for Chrome, Safari and Opera */
.theback::-webkit-scrollbar {
  display: none;
}

/*******************
      STARS
*********************/

.flag {
  height: 54px;
  width: 70px;
}

/*******************
      STARS
*********************/

.stars {
  justify-content: center;
}
.stars * {
  color: gold;
}


.content{
  width: 200px;
}
</style>
Footer
