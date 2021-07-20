<template>
  <div id="app">
    <Header />
    <Main :film="film"/>
  </div>
</template>

<script>
import axios from "axios";
import Header from './components/Header.vue';
import Main from './components/Main.vue';



export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
    return {
      filteredFilm: [],
      film: [],
    }
  },
  created() {
    axios.get("https://api.themoviedb.org/3/movie/popular?api_key=7d3154d492e3c72fd9ee0846bf2ce25c").then((results) => {
      this.film = results.data.results;
      this.filteredMovies = results.data.results
    })
  },
  methods: {
    searchFilm (searchString){
      if (searchString.lenght == 0){
        this.filteredMovies = this.film
        return;
      }
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=7d3154d492e3c72fd9ee0846bf2ce25c&query=${searchString}`).then((results) => {
      this.film = results.data.results;
      })
    }
  },
}
</script>

<style lang="scss">

</style>
