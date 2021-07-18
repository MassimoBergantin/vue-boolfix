<template>
  <div id="app">
    <Header />
    <Main :film="film"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';



export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      films: [],
    }
  },
  created() {
    axios.get('https://api.themoviedb.org/3/search/movie?api_key=4cabd8f1c186c089b648088ba73c6791&language=en-US&query=ritorno-al-futuro&page=1&include_adult=false').then((result) => {
      this.films = result.data
    })
  }
}
</script>

<style lang="scss">

</style>
