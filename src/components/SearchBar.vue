<template>
  <input class="search-bar" type="text" placeholder="Search for a pokemon..." />
</template>

<script>
// import pokeApi from '../services/pokeApi';

export default {
  name: 'SearchBar',

  data() {
    return {}
  }
};
</script>

<style scoped>
.search-bar {
  padding: 1rem;
  width: 20rem;

  border-radius: 2rem;
  font-size: 20px;
}
</style>