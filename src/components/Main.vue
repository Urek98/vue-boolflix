<template>
  <div>
    <h1>Movie Popular</h1>

    <div class="main-section flex">
      <MovieCard
        v-for="movie in movieList"
        :key="movie.id"
        :title="movie.title"
        :name="movie.name"
        :original_title="movie.original_title"
        :original_name="movie.original_name"
        :original_language="movie.original_language"
        :vote_average="movie.vote_average"
        :poster_path="movie.poster_path"
      />
    </div>
  </div>
</template>

<script>
import MovieCard from "./MovieCard.vue";

export default {
  name: "Main",
  components: {
    MovieCard,
  },
  props: {
    movieList: Array,
  },
};
</script>


<style scoped lang="scss">
h1{
    padding-left: 80px;
    font-family: 'Teko', sans-serif;
    color: greenyellow;
    background-color: rgb(73, 72, 72);
    padding-top: 20px;
}

.main-section {
  background-color: rgb(73, 72, 72);
  width: 100%;
  height: 100%;
  justify-content: space-around;
  flex-wrap: wrap;
  padding: 20px 40px;
}
</style>
