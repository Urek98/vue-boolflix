<template>
  <div class="nav-bar flex">
    <div class="logo">BOOLFLIX</div>
    <div class="search-section">
      <input type="text" placeholder="Search movie..."
        v-model="inputValue" @keyup.enter="$emit('search',inputValue)" />
      <button>Search</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {},
};
</script>


<style scoped lang="scss">
.nav-bar {
  width: 100%;
  background-color: rgb(27, 27, 27);
  color: white;
  height: 60px;
  align-items: center;
  justify-content: space-between;
  font-weight: bold;
  font-family: 'Teko', sans-serif;
  padding: 0 30px;
  color: greenyellow;
  .logo {
    font-size: 50px;
  }
  .search-section {
    input {
      font-size: 20px;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
        Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
        border-bottom: 2px solid greenyellow;
        background-color: rgb(27, 27, 27);
        padding: 2px;
        color: greenyellow;
    }
    button {
      font-size: 20px;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
        Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
      padding: 2px;
      background-color: rgb(27, 27, 27);
      border-radius:0 5px 5px 0;
      color: greenyellow;
      border-color: greenyellow;
    }
  }
}
</style>
