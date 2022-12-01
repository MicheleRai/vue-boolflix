<template>
  <main>
    <div>
      <h1
        v-if="arrMovies.length"
        class="section"
      >
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
        <li><h1>{{ objMovie.title }}</h1></li>
        <li>Titolo originale:{{ objMovie.original_title }}</li>
        <li>Lingua originale:{{ objMovie.original_language }}</li>
        <li>Voto:{{ objMovie.vote_average }}</li>
      </ul>
      <h1
        v-if="arrTv.length"
        class="section"
      >
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
        <li>
          <h1>{{ objTv.name }}</h1>
        </li>
        <li>Titolo originale:{{ objTv.original_name }}</li>
        <li>Lingua originale:{{ objTv.original_language }}</li>
        <li>Voto:{{ objTv.vote_average }}</li>
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
      display: flex;
      text-align: center;
      justify-content: center;
      flex-wrap: wrap;
      .section{
        flex: 0 0 100%;
      }
      ul{
        list-style: none;
        margin: 1rem;
        flex: 0 0 20%;
       li{
         background-color: white;

       }
      }
    }
  }
</style>
