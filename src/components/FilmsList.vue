<template>
  <div>
      <h2>FILMS</h2>
      <div class="container">
          <div class="row">
              <div class="card" v-for="film in films" :key="film.id">
                  <h3>{{ film.title }}</h3>
                  <h4>{{ film.original_title }}</h4>
                  <p>{{ film.original_language }}</p>
                  <p>{{ film.vote_average }}</p>
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