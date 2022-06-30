<template>
  <div id="app">

    <TheHeader @searchTextChanged="onSearchTextChanged"></TheHeader>

    <TheMain :moviesList="moviesList" :seriesList="seriesList"></TheMain>

    <MovieRating :vote="9.7"></MovieRating>


  </div>
</template>

<script>


import axios from 'axios';
import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';
import MovieRating from './components/MovieRating.vue';

export default {
  name: "App",
  components: {
    TheHeader,
    TheMain,
    MovieRating,
    
},

  data() {
    return {
      searchText: "",
      moviesList:[],
      seriesList:[]
    }
  },
  methods: {
    onSearchTextChanged(userInput) {
      this.searchText = userInput

      axios.get("https://api.themoviedb.org/3/search/movie/?api_key=06adf808dcf2297eee97f0494253138a", {
        params: {
          apiKey: "06adf808dcf2297eee97f0494253138a",
          query: userInput,
          language: "it-IT",

        },
      }) .then((resp) =>{
        this.moviesList = resp.data.results;
        this.seriesList = resp.data.results;

      })

    },

  },
}
</script>

<style lang="scss">

//@import "./assets/main.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
