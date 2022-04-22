<template>
<div>
     <div v-if="serieTv.poster_path !== null">
        <img :src="'https://image.tmdb.org/t/p/' + 'w342/' + serieTv.poster_path" :alt="serieTv.original_name">
     </div>
     <div v-else>Copertina non disponibile</div>
     <h3>{{ serieTv.name }}</h3>
     <h4>{{ serieTv.original_name }}</h4>
     <!--p>{{ serieTv.original_language }}</p-->
     <p>{{ serieTv.vote_average }}</p>
     <FlagComponent :flags="serieTv.original_language"/>
     <StarsComponent :voto="serieTv.vote_average"/>
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