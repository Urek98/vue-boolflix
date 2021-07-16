<template>
  <div class="card-container flex">
    <div class="card">
      <img
        src="https://image.tmdb.org/t/p/w342/hQq8xZe5uLjFzSBt4LanNP7SQjl.jpg"
        alt=""
      />
      <div class="movie-info">
        <div>Titolo</div>
        <div>Titolo originale</div>
        <div>Lingua</div>
        <div>Voto</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MovieCard",
  props: {},
};
</script>


<style scoped lang="scss">
.card-container {
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 40px;
  .card {
      :hover + .movie-info{
            display: block;
           transition: all 5s;
        }
    .movie-info{
        font-size: 24px;
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        color: white;
        position: relative;
        bottom: 30%;
        text-align: center;
        background-color: rgb(27,27,27,0.5);
        display: none;
        text-shadow: 4px 2px 7px rgba(0,0,0,0.9);
        :hover{
            display: block;
        }
        
        
    }
  }
}
</style>
