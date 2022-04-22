<template>
  <div>
    <h2>SERIES</h2>
    <div class="container">
        <div class="row">
            <div class="card" v-for="serieTv in series" :key="serieTv.id">
                <SerieItem :serieTv="serieTv"/>
            </div>
        </div>
    </div>
</div>
</template>

<script>
import SerieItem from './SerieItem.vue'
export default {
    name:'SeriesList',
    props:{
        series:Array
    },
    components:{
        SerieItem
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