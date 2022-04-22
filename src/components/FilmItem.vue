<template>
  <div>
        <div v-if="film.poster_path !== null">
            <img :src="'https://image.tmdb.org/t/p/' + 'w342/' + film.poster_path" :alt="film.title">
        </div>
        <div v-else>Copertina non disponibile</div>
        <h3>{{ film.title }}</h3>
        <h4>{{ film.original_title }}</h4>
        <p>{{ film.original_language }}</p>
        <p>{{ film.vote_average }}</p>
        <FlagComponent :flags="film.original_language"/>
        <div class="stellette">
            <div v-for="m in 5" :key="m">
                <div v-if="m < Math.ceil(film.vote_average / 2)"><i class="fa-solid fa-star"></i></div>
                <div v-else><i class="fa-regular fa-star"></i></div>
            </div>
        </div>
  </div>
</template>

<script>
import FlagComponent from './FlagComponent.vue'
export default {
    name:'FilmItem',
    props:{
        film:Object
    },
    components:{
        FlagComponent
    }
}
</script>

<style lang="scss" scoped>

 img{
     width:100%;
 }
.stellette{
            display:flex;
            justify-content: center;
         }
</style>