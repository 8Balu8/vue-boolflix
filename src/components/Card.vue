<template>
  <div class="card">
    <div class="poster">
      <img
        v-if="details.poster_path"
        :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`"
        alt="Movie Poster"
      />
      <img
        class="noposter"
        v-else
        :src="require(`../assets/img/noposter.png`)"
        alt="No poster"
      />
    </div>
    <div class="content-details">
      <ul>
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
            v-for="(val, i) in starsValue"
            :key="i"
          ></i>
          <i
            class="fas fa-star empty-star"
            v-for="(val, i) in emptyStars"
            :key="'A' + i"
          ></i>
        </li>
        <li>Overview: <br />{{ details.overview }}</li>
      </ul>
    </div>
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
      maxStars: 5,
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
      return this.maxStars - this.starsValue;
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  height: 500px;
  min-width: 330px;
  margin: 30px 3px;
  position: relative;

  .poster {
    height: 100%;
    overflow: hidden;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;

    &:hover {
      display: none;
    }

    img {
      width: 100%;
      height: 100%;
    }
  }

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
    color: #cbcbcb;
  }
  .content-details {
    width: 330px;
    padding: 10px;
    height: 100%;
    background-color: gray;
    overflow-y: auto;
    position: absolute;
    top: 0;
    left: 0;

    &:hover {
      z-index: 2;
    }
  }
  .noposter {
    width: 100%;
  }
}
</style>