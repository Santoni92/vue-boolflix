<template>
  <div>
      <input type="text" v-model="query">
      <button @click="queryApi">Cerca</button>
  </div>
</template>

<script>
export default {
name:'SearchBar'
}
</script>

<style>

</style>