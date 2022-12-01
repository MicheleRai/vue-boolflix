<template>
  <body>
    <HeaderPage @queryChange="search" />
    <MainPage
      :arr-movies="arrMovies"
      :arr-tv="arrTv"
    />
  </body>
</template>

<script>
import axios from 'axios';
import HeaderPage from '@/components/HeaderPage.vue';
import MainPage from '@/components/MainPage.vue';
import Vue from 'vue';
import LangFlag from 'vue-lang-code-flags';

Vue.component('LangFlag', LangFlag);

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
      resultsLanguages: 'it-IT',
      arrMovies: [],
      arrTv: [],
    };
  },
  methods: {
    search(queryString) {
      axios.get(`${this.baseApiUrl}/search/movie`, {
        params: {
          api_key: this.apiKey,
          language: this.resultsLanguages,
          query: queryString,
        },
      })
        .then((responseAxios) => {
          this.arrMovies = responseAxios.data.results;
          console.log(this.arrMovies);
        });
      axios.get(`${this.baseApiUrl}/search/tv`, {
        params: {
          api_key: this.apiKey,
          language: this.resultsLanguages,
          query: queryString,
        },
      })
        .then((responseAxios) => {
          this.arrTv = responseAxios.data.results;
          console.log(this.arrTv);
        });
    },
  },
};
</script>

<style lang="scss">
  @import '@/assets/scss/reset'

</style>
