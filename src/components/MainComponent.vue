<template>
  <main>
    <FilmsList :films="films"/>
    <SeriesList :series="series"/>
  </main>
</template>

<script>
import FilmsList from './FilmsList.vue'
import SeriesList from './SeriesList.vue'
export default {
    name:'MainComponent',
    props:{
      films:Array,
      series:Array
    },
    components:{
      FilmsList,
      SeriesList
    }

}
</script>

<style>

</style>