<template>
<main>
    <div class="container">
        <div class="card-contain">
            <MovieCard :movies="movies"/>
        </div>
    </div>
</main>
</template>

<script>
import MovieCard from "../components/MovieCard.vue";
export default {
    name: "Main",
    components: {
        MovieCard
    },
    props: {
        movies: Array
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