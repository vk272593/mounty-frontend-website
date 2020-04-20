<template>
  <div id="main-component">
    <TopRatedMovies />
    <UpcomingMovies />
  </div>
</template>

<script>
import TopRatedMovies from "./components/TopRatedMovie.vue";
import UpcomingMovies from "./components/UpcomingMovies";

export default {
  name: "App",
  components: {
    TopRatedMovies,
    UpcomingMovies
  }
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background: rgb(57, 57, 57);
  color: #eadfdf;
}
* {
  box-sizing: border-box;
}
</style>
<style scoped>
#main-component {
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
}
#main-component div {
  width: 700px;
  flex-grow: 1;
}
</style>
