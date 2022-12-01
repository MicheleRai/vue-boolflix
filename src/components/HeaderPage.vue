<template>
  <header>
    <h1>BOOLFLIX</h1>
    <form @submit.prevent="$emit('queryChange', queryString)">
      <label for="query">
        <input
          id="query"
          v-model="queryString"
          type="text"
          name="query"
          placeholder="Cerca qualcosa da vedere"
        >
      </label>
      <button>
        Cerca
      </button>
    </form>
  </header>
</template>

<script>
export default {
  name: 'HeaderPage',
  data() {
    return {
      queryString: '',
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
