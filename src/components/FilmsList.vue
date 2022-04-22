<template>
  <div>
      <h2>FILMS</h2>
      <div class="container">
          <div class="row">
              <div class="card" v-for="film in films" :key="film.id">
                  <FilmItem :film="film"/>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import FilmItem from './FilmItem.vue'
export default {
    name:'FilmsList',
    props:{
        films:Array
    },
    data(){
        return{
                 "poster_sizes": [
                                    "w92",
                                    "w154",
                                    "w185",
                                    "w342",
                                    "w500",
                                    "w780",
                                    "original"
                                ],
        }
    },
    components:{
        FilmItem
    }
}
</script>

<style lang="scss" scoped>
.container{
    max-width: 1170px;
    margin: 0 auto;
    .row{
        display:flex;
        flex-wrap:wrap;
        .card{
            width:25%;
            padding: 0.5rem;
            border:1px solid #999;
            text-align: center;
        }
    }
}
</style>