<template>
  <div>
    <div class="card">
      <div
        v-if="film.poster_path !== null "
        :style="backgroundImageInlineStyle"
        class="background"
      >
        <!--img :src="'https://image.tmdb.org/t/p/' + 'w342/' + film.poster_path" :alt="film.title"-->
      </div>
      <div v-else>
        Copertina non disponibile
      </div>
    </div>
    <div class="informazioni">
       <h3>{{ film.title }}</h3>
       <h4>{{ film.original_title }}</h4>
       <p>{{ film.vote_average }}</p>
      <FlagComponent :flags="film.original_language" />
      <StarsComponent :voto="film.vote_average" />
    </div>
  </div>
</template>

<script>
import FlagComponent from "./FlagComponent.vue";
import StarsComponent from "./StarsComponent.vue";
export default {
  name: "FilmItem",
  props: {
    film: Object,
  },
  computed: {
    backgroundImageInlineStyle() {
      //console.log(`https://image.tmdb.org/t/p/w342/${this.film.poster_path}`);
      return `background-image: url(https://image.tmdb.org/t/p/w342/${this.film.poster_path})`;
    }
  },
  components: {
    FlagComponent,
    StarsComponent,
  },
};
</script>

<style lang="scss" scoped>

  .background {
    min-height: 342px;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }
  .informazioni{
    min-height: 342px;
    display:none;
  }
  .card:hover .background{
    display:none;
  }

  .card:hover .informazioni{
    display:block
  }
</style>
