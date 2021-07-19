<template>
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
.main-section {
  background-color: rgb(73, 72, 72);
  width: 100%;
  height: 100%;
  justify-content: space-around;
  flex-wrap: wrap;
  padding: 40px;
}
</style>
