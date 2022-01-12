<template>
<main>
    <div class="container">
        <h2>Film</h2>
        <MovieCard :movies="movies"/>
        <h2>Series</h2>
        <SeriesCard :series="series"/>
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
        SeriesCard
    },
    props: {
        movies: Array,
        series: Array
    },
    methods: {
        decimalAdjust: function(number) {
            return Math.floor(number)
        }
    }
}
</script>

<style lang="scss" scoped>
main {
    padding: 50px;
}
</style>