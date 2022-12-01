<template>
  <main>
    <div>
      <ul
        v-for="objMovie in arrMovies"
        :key="objMovie.id"
      >
        <li>{{ objMovie.title }}</li>
        <li>{{ objMovie.original_title }}</li>
        <li>{{ objMovie.original_lenguage }}</li>
        <li>{{ objMovie.vote_avarage }}</li>
      </ul>
    </div>
  </main>
</template>

<script>

export default {
  name: 'MainPage',
  props: {
    arrMovies: Array,
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
