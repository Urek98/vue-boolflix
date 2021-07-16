<template>
  <div class="main-section">
      <MovieCard/>
  </div>
    
</template>

<script>

import MovieCard from './MovieCard.vue'

export default {
  name: 'Main',
  components :{
      MovieCard
  },
  props: {
    
  }
}
</script>


<style scoped lang="scss">
    .main-section{
        background-color: grey;
        width: 100%;
        height: 100%;
    }
</style>
