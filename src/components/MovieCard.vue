<template>
  <div class="card-container">
    <div class="card">
      <img class="poster" :src="poster(poster_path)" alt="poster" />
      <div class="movie-info flex">
        <div>{{ title }} {{ name }}</div>
        <div>{{ original_title }} {{ original_name }}</div>
        <img class="flag" :src="flag(original_language)" alt="flag" />
        <div>
          <span v-for="x in 5" :key="x">
            <i :class="checkStar(x)"></i>
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
        if(poster_path == null) {
            return "https://via.placeholder.com/342x513.png?text=Poster+not+avabile"
        } else {
            return "https://image.tmdb.org/t/p/w342" + poster_path;

        }
    },
    flag(original_Language) {
      return require("../assets/" + original_Language + ".png");
    },
    checkStar: function (x) {
      if (x <= this.vote) {
        return "fas fa-star";
      } else {
        return "far fa-star";
      }
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
    .poster {
      width: 342px;
      height: 513px;
    }
    &:hover .movie-info {
      display: block;
    }
    .movie-info {
      padding: 100px 40px 0 40px;
      font-size: 24px;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
        Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
      color: white;
      height: 100%;
      position: relative;
      bottom: 101%;
      width: 342px;
      text-align: center;
      background-color: rgb(27, 27, 27, 0.5);
      justify-content: center;
      flex-direction: column;
      text-shadow: 4px 2px 7px rgba(0, 0, 0, 0.9);
      display: none;

      .flag {
        width: 40px;
        margin: 0 auto;
      }
    }
  }
}
</style>
