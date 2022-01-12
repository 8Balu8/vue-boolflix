<template>
  <div id="app">
    <Header @getUserSearch="getMovieAndSeries"/>
    <Main :movies="movies" :series="series"/>
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
      seriesEndPoint: "/search/tv",
      apiKey: "?api_key=d25703f25aaa953856af5ee2ef9120fd",
      movies: [],
      series: []
    }
  },
  methods: {
    getMovieAndSeries(userSearch) {
      let userQuery = "&query="+userSearch
      axios.get(this.apiUrl+this.movieEndPoint+this.apiKey+userQuery).then((response) => {
        this.movies = response.data.results
      })
      axios.get(this.apiUrl+this.seriesEndPoint+this.apiKey+userQuery).then((response) => {
        this.series = response.data.results
      })
    }
  }
};
</script>

<style lang="scss">
@import "./styles/general"
</style>
