<template>
  <div class="stellette">
    <div v-for="m in 5" :key="m">
        <div v-if="m <= Math.ceil(voto / 2)"><i class="fa-solid fa-star"></i></div>
        <div v-else><i class="fa-regular fa-star"></i></div>
    </div>
</div>
</template>

<script>
export default {
    name:'StarsComponent',
    props:{
        voto:Number
    }
}
</script>

<style scoped>
.stellette{
            display:flex;
            justify-content: center;
         }
</style>