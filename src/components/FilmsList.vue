<template>
  <div>
      <h2>FILMS</h2>
      <div class="container">
          <div class="row">
              <div class="card" v-for="film in films" :key="film.id">
                  <div v-if="film.poster_path !== null">
                      <img :src="'https://image.tmdb.org/t/p/' + 'w92/' + film.poster_path" :alt="film.title">
                  </div>
                  <div v-else>Copertina non disponibile</div>
                  <h3>{{ film.title }}</h3>
                  <h4>{{ film.original_title }}</h4>
                  <p>{{ film.original_language }}</p>
                  <p>{{ film.vote_average }}</p>
                  <div class="stellette">
                      <div v-for="m in 5" :key="m">
                        <div v-if="m < Math.ceil(film.vote_average / 2)"><i class="fa-solid fa-star"></i></div>
                        <div v-else><i class="fa-regular fa-star"></i></div>
                      </div>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
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
               // fattoreDiScala : 2, // (10/5)
                //numeroTotaleStellette : 5, 
               // numeroStellettePiene: Math.floor()
        }
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
                img{
                    width:100%;
                }
            }
        }
    }
    .stellette{
        display:flex;
    }
</style>