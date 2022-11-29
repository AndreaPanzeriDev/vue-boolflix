<template>
  <div id="app">
    <HeaderComp @search="emitInputFilmName"/>
    <MainComp :arrayFilmFull="FilmsArray"/>  <!--Send the info to MainComp (child) -->
  </div>
</template>

<script>

import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data(){
    return{
      FilmName: '',
      FilmsArray: [],
    }
  },
  mounted(){

  },
  methods:{
    emitInputFilmName(valoreEmit){
      this.FilmName = valoreEmit
      //call the function that search all the film spect
      this.getInfoFilm();
    },

    getInfoFilm(){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=c71ccc51695322240e536d0ad92b6f3c&language=en-US&page=1&include_adult=false&query=' + this.FilmName).then( (response) => {
        this.FilmsArray = response.data.results
      } )
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;color: #2c3e50;
}

</style>
