<template>
<div>
    <div class="card">
        <div v-if="serieTv.poster_path !== null"  :style="backgroundImageInlineStyle"
             class="background">
        </div>
        <div v-else>Copertina non disponibile</div>
    </div>
    <div class="informazioni">
        <h3>{{ serieTv.name }}</h3>
        <h4>{{ serieTv.original_name }}</h4>
        <!--p>{{ serieTv.original_language }}</p-->
        <p>{{ serieTv.vote_average }}</p>
        <FlagComponent :flags="serieTv.original_language"/>
        <StarsComponent :voto="serieTv.vote_average"/>
    </div>  
</div>
</template>

<script>
import FlagComponent from './FlagComponent.vue'
import StarsComponent from './StarsComponent.vue'
export default {
    name:'SerieItem',
    props:{
        serieTv:Object
    },
     computed: {
                backgroundImageInlineStyle()
                 {
                     //console.log(`https://image.tmdb.org/t/p/w342/${this.film.poster_path}`);
                     return `background-image: url(https://image.tmdb.org/t/p/w342/${this.serieTv.poster_path})`;
                 }
             },
    components:{
        FlagComponent,
        StarsComponent
    }
}
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