<template>
  <div id="movies-card">
    <div class="image">
      <img :src="imgSrc+ movieDetails.poster_path" alt="poster" />
    </div>
    <div class="details">
      <h2>{{movieDetails.title}}</h2>
      <div class="highlight">
        <strong>Vote:</strong>
        {{movieDetails.vote_average}}
      </div>
      <div class="highlight">
        <strong>No. of Voters:</strong>
        {{movieDetails.vote_count}}
      </div>
      <div class="highlight">
        <strong>Popularity:</strong>
        {{movieDetails.popularity}}
      </div>
      <p>
        <strong>Overview:</strong>
        {{movieDetails.overview}}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "MoviesCard",
  props: ["movieDetails"],
  data() {
    return {
      imgSrc: "https://image.tmdb.org/t/p/w220_and_h330_face/"
    };
  }
};
</script>

<style scoped>
#movies-card {
  max-height: 300px;
  margin: 20px 10px;
  padding: 0;
  display: flex;
  justify-content: flex-start;
  flex-wrap: nowrap;
  flex-flow: row;
  background: rgb(80, 80, 80);
  color: #5de1ed;
}
.details {
  margin: 0 20px 15px 20px;
  overflow: auto;
}
.image {
  max-height: 300px;
}
img {
  height: 100%;
}
.highlight {
  font-style: italic;
}
h2 {
  color: #a4f6fd;
  font-weight: 500;
  font-size: 25px;
  margin: 10px 0;
}
</style>
