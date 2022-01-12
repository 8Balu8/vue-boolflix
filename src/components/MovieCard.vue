<template>
    <div class="card-contain">
        <div class="card" v-for="movie, index in movies" :key="index">
            <ul>
                <li>Title: {{movie.title}}</li>
                <li>Original Title: {{movie.original_title}}</li>
                <li class="flag">
                    Language: <img :src="require(`../assets/img/${movie.original_language}.png`)" :alt="movie.original_language">
                </li>
                <li>Vote: {{movie.vote_average}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "MovieCard",
    props: {
        movies: Array
    }
}
</script>

<style lang="scss" scoped>
.card-contain {
    display: flex;
    flex-wrap: wrap;

    .card {
        width: calc((100% / 3) - 40px);
        margin: 10px 20px;

        .flag {
            width: 30px;
            display: flex;

            img {
                width: 100%;
                margin-left: 5px;
            }
        }
    }
}

</style>