<template>
  <div>
    <h2>SERIES</h2>
    <div class="container">
        <div class="row">
            <div class="card" v-for="serieTv in series" :key="serieTv.id">
                <h3>{{ serieTv.name }}</h3>
                <h4>{{ serieTv.original_name }}</h4>
                <p>{{ serieTv.original_language }}</p>
                <p>{{ serieTv.vote_average }}</p>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name:'SeriesList',
    props:{
        series:Array
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