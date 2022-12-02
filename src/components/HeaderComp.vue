<template>
  <div id="header">
    <img src="./Logonetflix.png" alt="logo">
    <div class="align-self-center">
      <input type="text" v-model="textToSearch" placeholder="Insert a title" @keyup="sendTextFilm">
    </div>
  </div>
</template>

<script>
export default {
    name: 'HeaderComp',
    components:{

    },
    data(){
      return{
        textToSearch: '',
      }
    },
    mounted(){
      this.sendTextFilm();
    },
    methods:{
      sendTextFilm(){
        this.$emit('search', this.textToSearch)
      }
    }
}
</script>

<style scoped>
#header{
  display: flex;
  justify-content: space-between;
  height: 5rem;
}
</style>