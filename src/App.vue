<template>
  <body>
    <HeaderPage @queryChange="search" />
    <MainPage :arr-movies="arrMovies" />
  </body>
</template>

<script>
import axios from 'axios';
import HeaderPage from '@/components/HeaderPage.vue';
import MainPage from '@/components/MainPage.vue';

export default {
  name: 'App',

  components: {
    HeaderPage,
    MainPage,
  },
  data() {
    return {
      baseApiUrl: 'https://api.themoviedb.org/3',
      apiKey: 'ce50709de8103dbd86e95807b64b0b75',
      resultsLanguage: 'it-IT',
      arrMovies: [],
    };
  },
  methods: {
    search(queryString) {
      axios.get(`${this.baseApiUrl}/search/movie`, {
        params: {
          api_Key: this.apiKey,
          query: queryString,
          language: this.resultsLanguage,
        },
      })
        .then((responseAxios) => {
          this.arrMovies = responseAxios.data.results;
          console.log(this.arrMovies);
        });
    },
  },
};
</script>

<style lang="scss">
  @import '@/assets/scss/reset'

</style>
