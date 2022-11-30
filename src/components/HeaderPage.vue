<template>
  <header>
    <h1>BOOLFLIX</h1>
    <label for="s">
      <input
        id="s"
        v-model="searchString"
        type="text"
        name="s"
        placeholder="Cerca qualcosa da vedere"
        @keyup.enter="search"
      >
      <button @click="search">
        Cerca
      </button>
    </label>
  </header>
</template>

<script>
export default {
  name: 'HeaderPage',
  data() {
    return {
      searchString: '',
    };
  },
  methods: {
    search() {
      this.$emit('search', this.searchString);
    },
  },
};
</script>

<style lang="scss" scoped>
header{
  background-color: black;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem;
  max-width: 1200px;
  width: 100%;

  h1{
    color: red;
  }
}
</style>
