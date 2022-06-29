<template>
  <div id="app">

    <TheHeader @searchTextChanged="onSearchTextChanged"></TheHeader>

    <TheMain :moviesList="moviesList"></TheMain>

  </div>
</template>

<script>


import axios from 'axios';
import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';

export default {
  name: "App",
  components: {
    TheHeader,
    TheMain,
  },

  data() {
    return {
      searchText: "",
      moviesList:[]
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
        this.serieLists = resp.data.results

      })

    },

  },
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
