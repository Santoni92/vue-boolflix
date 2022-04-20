<template>
  <div>
      <input type="text" v-model="filmRichiesto">
      <button @click="$emit('searchEmit',filmRichiesto)">Cerca</button>
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

<style>

</style>