<template>
  <div class="card-container">
    <div class="card">
      <img :src="poster(poster_path)" alt="" />
      <div class="movie-info flex">
        <div>{{ title }} {{ name }}</div>
        <div>{{ original_title }} {{ original_name }}</div>
        <img class="flag" :src="flag(original_language)" alt="" />
        <div>{{ vote }}</div>
        <div>
          <span>
            <i v-if="vote > 0" class="fas fa-star"></i>
            <i v-else class="far fa-star"></i>
          </span>
          <span>
            <i v-if="vote > 1" class="fas fa-star"></i>
            <i v-else class="far fa-star"></i>
          </span>
          <span>
            <i v-if="vote > 2" class="fas fa-star"></i>
            <i v-else class="far fa-star"></i>
          </span>
          <span>
            <i v-if="vote > 3" class="fas fa-star"></i>
            <i v-else class="far fa-star"></i>
          </span>
          <span>
            <i v-if="vote > 4" class="fas fa-star"></i>
            <i v-else class="far fa-star"></i>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MovieCard",
  props: {
    title: String,
    name: String,
    original_title: String,
    original_name: String,
    original_language: String,
    poster_path: String,
    vote_average: Number,
  },
  data() {
    return {
      vote: Math.round(this.vote_average / 2),
    };
  },
  methods: {
    
    poster(poster_path) {
      return "https://image.tmdb.org/t/p/w342" + poster_path;
    },
    flag(original_Language) {
      return require("../assets/" + original_Language + ".png");
    },
  },
};
</script>


<style scoped lang="scss">
.card-container {
  padding-bottom: 20px;
  .card {
    height: 513px;
    width: 100%;

    .movie-info {
      height: 100%;
      font-size: 24px;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
        Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
      color: white;
      position: relative;
      bottom: 100%;
      width: 342px;
      text-align: center;
      background-color: rgb(27, 27, 27, 0.5);
      justify-content: center;
      flex-direction: column;
      text-shadow: 4px 2px 7px rgba(0, 0, 0, 0.9);

      .flag {
        width: 40px;
        margin: 0 auto;
      }
    }
  }
}
</style>
