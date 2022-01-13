<template>
  <main>
    <div class="container">
      <h2>Film</h2>
      <div class="card-contain">
        <Card v-for="movie in movies" :key="movie.id" :details="movie" />
      </div>
      <h2>Series</h2>
      <div class="card-contain">
        <Card v-for="tv in series" :key="tv.id" :details="tv" />
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
  padding: 50px;

  .card-contain {
    display: flex;
    flex-wrap: wrap;
  }
}
</style>