<template>
  <main>
    <div>
      <h1
        v-if="arrMovies.length"
        class="section"
      >
        MOVIE
      </h1>
      <div
        v-for="objMovie in arrMovies"
        :key="objMovie.id"
        class="container"
      >
        <img
          :src="'https://image.tmdb.org/t/p/w342/' + objMovie.poster_path"
          alt="img"
        >
        <ul>
          <li><h1>{{ objMovie.title }}</h1></li>
          <li><strong>Titolo originale:</strong>{{ objMovie.original_title }}</li>
          <li>
            <strong>Lingua originale:</strong><lang-flag
              :iso="objMovie.original_language"
            />
          </li>
          <li>
            <strong>Voto:</strong>
            <font-awesome-icon
              v-for="stars in (parseInt(objMovie.vote_average / 2))"
              :key="stars"
              icon="fa-solid fa-star"
              style="color:gold"
            />
            <font-awesome-icon
              v-for="stars in (5 - parseInt(objMovie.vote_average / 2))"
              :key="(stars + 5)"
              icon="fa-regular fa-star"
              style="color:white"
            />
          </li>
          <li><strong>Trama:</strong> {{ objMovie.overview }}</li>
        </ul>
      </div>
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
        <li>
          Lingua originale:<lang-flag
            :iso="objTv.original_language"
          />
        </li>
        <li><strong>Trama:</strong> {{ objTv.overview }}</li>
        <li><strong>Voto:</strong>{{ objTv.vote_average }}</li>
      </ul>
    </div>
  </main>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

export default {
  name: 'MainPage',
  components: {
    LangFlag,
  },
  props: {
    arrMovies: Array,
    arrTv: Array,
  },
  data() {
    return {
    };
  },
  methods: {

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
      justify-content: center;
      flex-wrap: wrap;
      .section{
        flex: 0 0 100%;
        text-align: center;
      }
      .container{
        margin: 1rem;
        flex: 0 0 26.3%;
        border: 2px solid white;
        ul{
          list-style: none;
          height: 80%;
          display: none;
          align-items: flex-start;
          flex-direction: column;
          color: white;
          padding: 1.5rem;
        }
      }
      .container:hover img{
          display: none;
        }
        .container:hover ul{
          display: flex;
        }
        .container:hover{
          background-color: black;
        }
    }
  }
</style>
