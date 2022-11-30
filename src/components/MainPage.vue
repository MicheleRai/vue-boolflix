<template>
  <main>
    <div
      v-for="objMovie in arrFilm"
      :key="objMovie.title"
      :movie-info="objMovie"
    >
      <img
        key="objMovie.title"
        :src="'https://image.tmdb.org/t/p/w342'+objMovie.poster_path"
        :alt="img+objMovie.title"
      >
      <div class="info">
        <h3>{{ objMovie.title }}</h3>
        <p>titolo originale: {{ objMovie.original_title }}</p>
        <p>lingua: {{ objMovie.original_language }}</p>
        <p>voto: {{ objMovie.vote_average }}</p>
      </div>
    </div>
  </main>
</template>

<script>

import axios from 'axios';

export default {
  name: 'MainPage',
  data() {
    return {
      urlApi: 'https://api.themoviedb.org/3/search/movie?api_key=ce50709de8103dbd86e95807b64b0b75&query=fight',
      arrFilm: null,
      img: '',
    };
  },
  created() {
    axios.get(this.urlApi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        this.arrFilm = axiosResponse.data.results;
      });
  },
};
</script>

<style lang="scss" scoped>
  main{
    background-color: gray;
    min-height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    div{
      margin: 1rem;
      display: flex;
      flex-direction: column;
      text-align: center;
      .info{
        background-color: white;
      }
    }
  }
</style>
