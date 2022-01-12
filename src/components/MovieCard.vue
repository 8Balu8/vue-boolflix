<template>
  <div class="card">
    <ul>
      <li>
        <img
          :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`"
          alt="Movie Poster"
        />
      </li>
      <li>Title: {{ movie.title }}</li>
      <li>Original Title: {{ movie.original_title }}</li>
      <li class="flag">
        Language:
        <img
          v-if="flagImg.includes(movie.original_language)"
          :src="require(`../assets/img/${movie.original_language}.png`)"
          :alt="movie.original_language"
        />
        <span v-else>{{ movie.original_language }}</span>
      </li>
      <li>
        Vote:
        <i
          class="fas fa-star full-star"
          v-for="val in starsValue"
          :key="val"
        ></i>
        <i
          class="fas fa-star empty-star"
          v-for="val in emptyStars"
          :key="val"
        ></i>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MovieCard",
  data: function () {
    return {
      flagImg: [
        "de",
        "el",
        "en",
        "es",
        "fr",
        "it",
        "hi",
        "hr",
        "ja",
        "ko",
        "pt",
        "sv",
      ],
      emptyNumber: 5,
    };
  },
  props: {
    movie: Object,
  },
  computed: {
    starsValue() {
      return Math.ceil(this.movie.vote_average / 2);
    },
    emptyStars() {
      return this.emptyNumber - this.starsValue;
    },
  },
};
</script>

<style lang="scss" scoped>
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
  .full-star {
    color: #e5e619;
  }
  .empty-star {
    color: gray;
  }
}
</style>