<template>
  <div id="app">
    <Header @getUserSearch="getMovie"/>
    <Main :movies="movies"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios"

export default {
  name: "App",
  components: {
    Header,
    Main
  },
  data: function() {
    return {
      apiUrl: "https://api.themoviedb.org/3",
      movieEndPoint: "/search/movie",
      apiKey: "?api_key=d25703f25aaa953856af5ee2ef9120fd",
      movies: [],
    }
  },
  methods: {
    getMovie(userSearch) {
      let userQuery = "&query="+userSearch
      axios.get(this.apiUrl+this.movieEndPoint+this.apiKey+userQuery).then((response) => {
        this.movies = response.data.results
      })
    }
  }
};
</script>

<style lang="scss">
@import "./styles/general"
</style>
