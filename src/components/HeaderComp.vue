<template>
  <div>
    <div>
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

<style>

</style>