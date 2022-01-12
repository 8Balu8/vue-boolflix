<template>
  <main>
    <div class="container">
      <h2>Film</h2>
      <div class="card-contain">
        <MovieCard
          v-for="(movie, index) in movies"
          :key="index"
          :movie="movie"
        />
      </div>
      <h2>Series</h2>
      <SeriesCard :series="series" />
    </div>
  </main>
</template>

<script>
import MovieCard from "../components/MovieCard.vue";
import SeriesCard from "../components/SeriesCard.vue";
export default {
  name: "Main",
  components: {
    MovieCard,
    SeriesCard,
  },
  props: {
    movies: Array,
    series: Array,
  },
};
</script>

<style lang="scss" scoped>
main {
  padding: 50px;

  .card-contain {
    display: flex;
    flex-wrap: wrap;
  }
}
</style>