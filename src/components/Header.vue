<template>
  <div class="nav-bar flex">
    <div class="logo" >BOOLFLIX</div>
    <div class="search-section">
      <input type="text" placeholder="Search..."
        v-model="inputValue" @keyup.enter="$emit('search',inputValue)" />
      <button @click="$emit('search',inputValue)"><i class="fas fa-search"></i></button>
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
      font-size: 24px;
      font-family: 'Teko', sans-serif;
        border-bottom: 2px solid greenyellow;
        background-color: rgb(27, 27, 27);
        padding: 2px 0 2px 20px;
        color: greenyellow;
    }
    button {
      font-size: 20px;
      padding: 5px 25px;
      background-color: rgb(27, 27, 27);
      border-radius:0 5px 5px 0;
      color: greenyellow;
      border-color: greenyellow;
    }
  }
}
</style>
