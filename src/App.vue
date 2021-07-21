<template>
  <div id="app">
    <Header @search="searchResult"  />
    <Main :movieList="movieList" />
  </div>
</template>

<script>
import axios from "axios";
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      movieList: [],
    };
  },
  created() {
      this.getApiMovie();
  },
  methods: {
    getApiMovie() {
      axios.get("https://api.themoviedb.org/3/movie/popular?api_key=62aed4b36495873a9f59552a12b9c758&").then((result) => {
        this.movieList = result.data.results;
      });
    },

    searchResult(inputValue) {
      if(inputValue.length == 0) {
        this.getApiMovie();
      } else {
      axios.get(`https://api.themoviedb.org/3/search/multi/?api_key=62aed4b36495873a9f59552a12b9c758&query=${inputValue}`).then((result) => {
          this.movieList = result.data.results;
        });
      }
    },                                       
  }
};
</script>

<style lang="scss">
@import "./style/app.scss";
</style>
