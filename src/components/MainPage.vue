<template>
  <main>
    <div>
      <h1 v-if="arrMovies.length">
        MOVIE
      </h1>
      <ul
        v-for="objMovie in arrMovies"
        :key="objMovie.id"
      >
        <img
          :src="'https://image.tmdb.org/t/p/w342/' + objMovie.poster_path"
          alt="img"
        >
        <li>{{ objMovie.title }}</li>
        <li>{{ objMovie.original_title }}</li>
        <li>{{ objMovie.original_language }}</li>
        <li>{{ objMovie.vote_average }}</li>
      </ul>
      <h1 v-if="arrTv.length">
        SERIE TV
      </h1>
      <ul
        v-for="objTv in arrTv"
        :key="objTv.id"
      >
        <img
          :src="'https://image.tmdb.org/t/p/w342/' + objTv.poster_path"
          alt="img"
        >
        <li>{{ objTv.name }}</li>
        <li>{{ objTv.original_name }}</li>
        <li>{{ objTv.original_language }}</li>
        <li>{{ objTv.vote_average }}</li>
      </ul>
    </div>
  </main>
</template>

<script>

export default {
  name: 'MainPage',
  props: {
    arrMovies: Array,
    arrTv: Array,
  },
  data() {
    return {
    };
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
      // .info{
      //   background-color: white;
      // }
    }
  }
</style>
