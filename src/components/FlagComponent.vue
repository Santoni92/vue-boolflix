<template>
  <p>
      <!--img class="flags" :src="`./img/${film.original_language}_flag.png`" alt=""-->
      <img v-if="hasImage" @error="imageError($event)" :src="`./img/${flags}_flag.png`" :alt="flags" class="flags">
      <span v-else>{{ flags }}</span>
  </p>
</template>

<script>
export default {
    name:'FlagComponent',
    props:{
        flags:String
    },
    data(){
        return{hasError: false,
                availableFlags: ['it','en','de','es','fr','ja','pt']
        }
    },
    methods:{
        imageError(event){
            event.target.style.display = 'none';
            this.hasError = true;
        }
    },
    computed:{
        hasImage(){
            return this.availableFlags.includes(this.flags);
        }
    }
}
</script>

<style lang="scss" scoped>
.flags{
        width:20px;
        }

</style>