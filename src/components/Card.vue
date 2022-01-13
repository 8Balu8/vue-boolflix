<template>
  <div class="card">
    <ul>
      <li>
        <img
          :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`"
          alt="Movie Poster"
        />
      </li>
      <li>Title: {{ details.title || details.name }}</li>
      <li>
        Original Title: {{ details.original_title || details.original_name }}
      </li>
      <li class="flag">
        Language:
        <img
          v-if="flagImg.includes(details.original_language)"
          :src="require(`../assets/img/${details.original_language}.png`)"
          :alt="details.original_language"
        />
        <span class="language" v-else>{{ details.original_language }}</span>
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
  name: "Card",
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
    details: Object,
  },
  computed: {
    starsValue() {
      return Math.ceil(this.details.vote_average / 2);
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
    width: 40px;
    display: flex;

    img {
      width: 100%;
      height: 20px;
      margin-left: 5px;
    }

    .language {
      margin-left: 10px;
      font-size: 16px;
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