<template>
  <main>
    <div class="container">
      <div v-if="movies.length > 0 || series.length > 0">
        <h2>Film</h2>
        <div class="card-contain">
          <Card v-for="movie in movies" :key="movie.id" :details="movie" />
        </div>
        <h2>Series</h2>
        <div class="card-contain">
          <Card v-for="tv in series" :key="tv.id" :details="tv" />
        </div>
      </div>
      <div v-else class="user-message">
        <h2>Make a research to see films and seriesTV</h2>
      </div>
    </div>
  </main>
</template>

<script>
import Card from "../components/Card.vue";
export default {
  name: "Main",
  components: {
    Card,
  },
  props: {
    movies: Array,
    series: Array,
  },
};
</script>

<style lang="scss" scoped>
main {
  background-color: black;
  color: white;
  padding-top: 150px;
  height: 100%;

  .user-message {
    text-align: center;
    font-size: 35px;
    height: 100vh;

    h2 {
      line-height: 50vh;
    }
  }

  h2 {
    margin-left: 3px;
    font-size: 30px;
  }

  .card-contain {
    display: flex;
    flex-shrink: 0;
    overflow-x: auto;
  }
}
</style>