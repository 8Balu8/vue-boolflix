<template>
  <div id="app">
    <Header @getUserSearch="userSearch"/>
    <Main/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
// import axios from "axios"

export default {
  name: "App",
  components: {
    Header,
    Main
  },
  data: function() {
    return {
      apiUrl: "https://developers.themoviedb.org/3",
      apiKey: "d25703f25aaa953856af5ee2ef9120fd",
      movieEndPoint: "/search/movie",
      query: this.userSearch
    }
  }
};
</script>

<style lang="scss">
@import "./styles/general"
</style>
