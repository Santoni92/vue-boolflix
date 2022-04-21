<template>
  <div class="header">
      <h1>BoolFlix</h1>
      <div>
          <input type="text" placeholder="Ricerca per titolo" v-model="filmRichiesto">
          <button @click="$emit('searchEmit',filmRichiesto)">Cerca</button>
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
    .header{
        display:flex;
        background-color:black;
        color:red;
    }
</style>