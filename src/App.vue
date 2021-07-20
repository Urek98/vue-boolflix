<template>
  <div id="app">
    <Header @search="searchResult" @clickLogo="getPopular"/>
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
    axios
      .get(
        "https://api.themoviedb.org/3/movie/popular?api_key=62aed4b36495873a9f59552a12b9c758&"
      )
      .then((result) => {
        this.movieList = result.data.results;
        this.inputValue = "";
      });
  },
  methods: {
    searchResult(inputValue) {
      axios
        .get(
          `https://api.themoviedb.org/3/search/multi/?api_key=62aed4b36495873a9f59552a12b9c758&query=${inputValue}`
        )
        .then((result) => {
          this.movieList = result.data.results;
        });
    },
    getPopular() {
    axios
      .get(
        "https://api.themoviedb.org/3/movie/popular?api_key=62aed4b36495873a9f59552a12b9c758&"
      )
      .then((result) => {
        this.movieList = result.data.results;
      });  
    }
  },
};
</script>

<style lang="scss">
@import "./style/app.scss";
</style>
