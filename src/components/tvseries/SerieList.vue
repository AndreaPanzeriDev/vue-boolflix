<template>
  <div id="cards">
    <CardComp v-for="(elem, index) in arraySeriesFull" :key="index" :singleItem="elem"/>
  </div>
</template>

<script>

import CardComp from './CardComp.vue'

export default {
    name: 'SerieList',
    components:{
        CardComp
    },
    props:{
      arraySeriesFull: Array
    }
}
</script>

<style>
#cards{
  width: 95%;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
}
</style>