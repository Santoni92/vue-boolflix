<template>
  <div id="app">
    <HeaderComponent @searchEmit="cercaFilm"/>
    <MainComponent :films="films"/>
  </div>
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue';
import MainComponent from'./components/MainComponent.vue';
import axios from 'axios';
export default {
  name: 'App',
  data(){
    return{
      apiUrl:'https://api.themoviedb.org/3/search/',
      apiKey:'f60679ff520c286ee002906fb58e4dbb',
      films:[],
      series:[]
    }
  },
  methods:{
    cercaFilm(filmRichiesto){
      if(filmRichiesto.length > 0){
         console.log('Ciò che HeaderComponent emette -->',filmRichiesto);
         const params = {
                          api_key: this.apiKey,
                          query: filmRichiesto,
                          language: 'it-IT'
                        }
         const  config = {params};     
         let url = this.apiUrl + 'movie';
         //chiamata axios per i film
         axios.get( url, config).then((response) => {
                                                    console.log('Risultato ritornatomi dalla chiamata api -->',response);
                                                    if(response.status === 200)
                                                    {
                                                      this.films = response.data.results;
                                                      console.log('array dei film -->',this.films);
                                                      console.log('singolo film -->',this.films[0]);
                                                    }
                                                    }).catch((error) => {
                                                                         console.log(error);
                                                                        });
         //chiamata axios per le serie tv
         url = this.apiUrl + 'tv'
         axios.get(url,config).then((response) => {
           if(response.status === 200)
           {
             this.series = response.data.results;
             console.log('array delle serie tv -->',this.series);
             console.log('singola serie tv -->',this.series[0]);
           }
         }).catch((error) => {
           console.log(error);
         })
      }
    }
  },
  components: {
    HeaderComponent,
    MainComponent
  }
}
</script>

<style lang="scss">
*{
  margin:0;
  padding:0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
