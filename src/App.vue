<template>
  <div id="app">
    <SearchBar @searchEmit="cercaFilm"/>
    <div v-for="film in filmCercato" :key="film.id">
      {{film.title}}
    </div>
    <!--Header/>
    <Main/-->
  </div>
</template>

<script>
//import Header from './components/Header.vue';
//import Main from'./components/Main.vue';
import SearchBar from '@/components/SearchBar.vue';
import axios from 'axios'
export default {
  name: 'App',
  data(){
    return{
      apiUrl:'https://api.themoviedb.org/3/search/',
      apiKey:'f60679ff520c286ee002906fb58e4dbb',
      filmRichiesto:'',
      films:[]
    }
  },
  mounted(){
    const params = {
        api_key: this.apiKey,
        query:'ritorno', //query: this.filmRichiesto,
        language: 'it-IT'
    }
    const  config = {params};     
    const url = this.apiUrl + 'movie';
    axios.get( url, config).then((response) => {
                                                  console.log(response);
                                                  this.films = response.data.results;
                                                  console.log(this.films[0]);
                                                }).catch((error) => {
                                                  console.log(error);
                                                 })
  },
  methods:{
    cercaFilm(filmRichiesto){
      this.filmRichiesto = filmRichiesto;
    }
  },
  computed:{
    filmCercato(){
      if(this.filmRichiesto === '')
      {
        return this.films;
      }
      return this.films.filter((item) =>{
        return item.title.includes(this.filmRichiesto);
      })
    }
  },
  components: {
    SearchBar,
    /*
    Header,
    Main*/
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
