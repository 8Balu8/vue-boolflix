<template>
  <main>
    <div class="container">
      <!-- FILM ROW SECTION -->
      <div v-if="movies.length > 0">
        <h2>Film</h2>
        <div class="card-contain">
          <Card v-for="movie in movies" :key="movie.id" :details="movie" />
        </div>
      </div>
      <!-- SERIES ROW SECTION -->
      <div class="series-contain" v-if="series.length > 0">
        <h2>Series</h2>
        <div class="card-contain">
          <Card v-for="tv in series" :key="tv.id" :details="tv" />
        </div>
      </div>
      <!-- Message for indication to user -->
      <div
        v-else-if="movie.length < 0 || series.length < 0"
        class="user-message"
      >
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
  height: 100vh;

  .user-message {
    text-align: center;
    font-size: 35px;
    height: 100vh;

    h2 {
      line-height: 50vh;
    }
  }

  h2 {
    margin-left: 10px;
    font-size: 30px;
  }

  .card-contain {
    display: flex;
    flex-shrink: 0;
    overflow-x: auto;
    margin-left: 10px;
  }

  .series-contain {
    background-color: black;
  }
}
</style>