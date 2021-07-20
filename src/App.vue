<template>
  <div id="app">
    <Header @search="searchMovies" />
    <Main :cards="cards"/>
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
      filteredMovies: [],
      cards: [],
    }
  },
  created() {
    axios.get("https://api.themoviedb.org/3/movie/popular?api_key=7d3154d492e3c72fd9ee0846bf2ce25c").then((results) => {
      this.cards = results.data.results;
      this.filteredMovies = results.data.results
    })
  },
  methods: {
    searchMovies (searchString){
      if (searchString.lenght == 0){
        this.filteredMovies = this.cards
        return;
      }
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=7d3154d492e3c72fd9ee0846bf2ce25c&query=${searchString}`).then((results) => {
      this.cards = results.data.results;
      })
    }
  },
}
</script>



<style lang="scss">
</style>