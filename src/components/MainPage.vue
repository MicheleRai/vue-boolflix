<template>
  <main>
    <div
      v-for="objMovie in arrFilm"
      :key="objMovie.title"
      :movie-info="objMovie"
    >
      <img
        :src="'https://image.tmdb.org/t/p/w300'+objMovie.poster_path"
        :alt="img+objMovie.title"
      >
      <h3>{{ objMovie.title }}</h3>
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
      h3{
        background-color: white;
      }
    }
  }
</style>
