<template>
  <div id="app">
    <!--SearchBar/>
    <Header/>
    <Main/-->
  </div>
</template>

<script>
//import Header from './components/Header.vue';
//import Main from'./components/Main.vue';
//import SearchBar from '@/components/SearchBar.vue';
import axios from 'axios'
export default {
  name: 'App',
  data(){
    return{
      apiUrl:'https://api.themoviedb.org/3/search/',
      apiKey:'f60679ff520c286ee002906fb58e4dbb',
      films:[]
    }
  },
  mounted(){
    const query = "ritorno";
    const params = {
      api_Key: this.apiKey,
      query,
      language:'it_IT'
    };
    axios.get(this.apiUrl + 'movie' ,{params}).then((response) => {
      console.log(response);
    }).catch((error) => {
      console.log(error);
    })
  },
  components: {
   /* SearchBar,
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
