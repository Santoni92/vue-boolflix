<template>
  <div>
        <div v-if="film.poster_path !== null">
            <img :src="'https://image.tmdb.org/t/p/' + 'w342/' + film.poster_path" :alt="film.title">
        </div>
        <div v-else>Copertina non disponibile</div>
        <h3>{{ film.title }}</h3>
        <h4>{{ film.original_title }}</h4>
        <p>{{ film.vote_average }}</p>
        <FlagComponent :flags="film.original_language"/>
        <StarsComponent :voto="film.vote_average"/>
  </div>
</template>

<script>
import FlagComponent from './FlagComponent.vue'
import StarsComponent from './StarsComponent.vue'
export default {
    name:'FilmItem',
    props:{
        film:Object
    },
    components:{
        FlagComponent,
        StarsComponent
    }
}
</script>

<style lang="scss" scoped>

 img{
     width:100%;
 }
</style>