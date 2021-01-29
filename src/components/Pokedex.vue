<template>
  <h1>Vue Pokedex</h1>
  <search-bar />
  <p>Click on any pokemon to see the details</p>
  <div id="pokedex">
    <div v-for="pokemon in pokemons" :key="pokemon.name">
     <pokemon :data="pokemon.data" />
    </div>
  </div>
</template>

<script>
import pokeApi from '../services/pokeApi';
import Pokemon from './Pokemon.vue';
import SearchBar from './SearchBar.vue';

export default {
  name: 'Pokedex',
  components: { SearchBar, Pokemon },

  data() {
    return {
      pokemons: null,
      pokemonQuery: String
    };
  },

  async mounted() {
    const pokemons = (await pokeApi.get('/pokemon?limit=100')).data.results;

    this.pokemons = await Promise.all(
      pokemons.map((pokemon) =>
        pokeApi.get(pokemon.url, { baseURL: '' }))
    );
  },
};
</script>

<style scoped>
#pokedex {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;

  margin-bottom: 2rem;
}
</style>