<template>
  <div id="app">
    <Header @search="searchFilm" />
    <Main :cards="cards" />
  </div>
</template>


<script>
import Header from "./components/Header.vue";
import axios from "axios";
import Main from "./components/Main.vue";
export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
    return {
      filteredFilm: [],
      cards: [],
    }
  },
  created() {
    axios.get("https://api.themoviedb.org/3/movie/popular?api_key=4cabd8f1c186c089b648088ba73c6791").then((results) => {
      this.cards = results.data.results;
      this.filteredFilm = results.data.results
    })
  },
  methods: {
    searchMovies (searchString){
      if (searchString.lenght == 0){
        this.filteredFilm = this.cards
        return;
      }
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=4cabd8f1c186c089b648088ba73c6791&query=${searchString}`).then((results) => {
      this.cards = results.data.results;
      })
    }
  },
}
</script>



<style lang="scss">
</style>