<template>
  <div class="upcoming-movies">
    <h1>Upcoming Movies</h1>
    <div v-bind:key="movieDetails.id" v-for="movieDetails in upcomingMovies">
      <MoviesCard v-bind:movieDetails="movieDetails" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import MoviesCard from "../assets/movieCard.vue";
export default {
  name: "UpcomingMovies",
  data() {
    return {
      upcomingMovies: []
    };
  },
  async created() {
    const end_point = "https://api.themoviedb.org/3/movie/upcoming";
    const api_key = "33f3b6e9a8fa34bf08cbe850e5d29ce0";
    await axios
      .get(`${end_point}?api_key=${api_key}`)
      .then(res => (this.upcomingMovies = res.data.results))
      .catch(err => console.log(err));
  },
  components: {
    MoviesCard
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  text-align: center;
  margin: 40px 0 0;
  color: #fff;
}
</style>
