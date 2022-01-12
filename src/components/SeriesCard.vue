<template>
    <div class="card-contain">
        <div class="card" v-for="series, index in series" :key="index">
            <ul>
                <li>
                    <img :src="`https://image.tmdb.org/t/p/w342${series.poster_path}`" alt="Series Poster">
                </li>
                <li>Title: {{series.name}}</li>
                <li>Original Title: {{series.original_name}}</li>
                <li class="flag">
                    Language: <img :src="require(`../assets/img/${series.original_language}.png`)" :alt="series.original_language">
                </li>
                <li>Vote: {{series.vote_average}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "SeriesCard",
    props: {
        series: Array
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