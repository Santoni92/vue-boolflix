<template>
<div class="container">
    <div class="header">
        <h1>BOOLFLIX</h1>
        <div>
            <input type="text" placeholder="Ricerca per titolo" v-model="filmRichiesto">
            <button @click="$emit('searchEmit',filmRichiesto)">Cerca</button>
        </div>  
    </div>
</div>
</template>

<script>
export default {
name:'SearchBar',
data(){
    return{
        filmRichiesto:''
    }
},
}
</script>

<style lang="scss" scoped>
.container{
    width:100%;
    max-width:1200px;
    margin: 0 auto;
    padding:30px;
    .header{
            display:flex;
            justify-content: space-between;
            align-items: center;
            color:red;
             }
}
   
   
   
   
   
   
</style>