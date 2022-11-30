<template>
  <main>
    dd
  </main>
</template>

<script>

import axios from 'axios';

export default {
  name: 'MainPage',
  data() {
    return {
      urlApi: 'https://api.themoviedb.org/3/movie/550?api_key=ce50709de8103dbd86e95807b64b0b75',
      arrFilm: null,
    };
  },
  created() {
    axios.get(this.urlApi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        // this.arrFilm = axiosResponse.data
      });
  },
};
</script>

<style lang="scss" scoped>

</style>
