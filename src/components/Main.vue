<template>
  <div>
    <div v-if="movieList.length == 0" class="sorry-section">
     <div>Sorry but there are no movies...</div> 
    </div>
    <div v-else class="main-section flex">
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
.sorry-section {
  padding: 20px 40px;
  background-color: rgb(73, 72, 72);
  width: 100%;
  height: calc(100vh - 60px);
  font-size: 40px;
  font-family: 'Teko', sans-serif;
  color: greenyellow;
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
