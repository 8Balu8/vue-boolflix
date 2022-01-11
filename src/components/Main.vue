<template>
<main>
    <div class="container">
        <div class="card-contain">
            <div class="card" v-for="movie, index in movies" :key="index">
                <ul>
                    <li>{{movie.title}}</li>
                    <li>{{movie.original_title}}</li>
                    <li>{{movie.original_language}}</li>
                    <li>{{movie.vote_average}}</li>
                </ul>
            </div>
        </div>
    </div>
</main>
</template>

<script>
export default {
    name: "Main",
    props: {
        movies: Array
    }
}
</script>

<style lang="scss" scoped>
main {
    padding: 50px;

    .card-contain {
        display: flex;
        flex-wrap: wrap;

        .card {
            width: calc((100% / 3) - 40px);
            margin: 10px 20px;
        }
    }
}
</style>