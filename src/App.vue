<template>
  <div id="app">
    <pokedex />
  </div>
</template>

<script>
import Pokedex from './components/Pokedex.vue';

export default {
  name: 'App',
  components: {
    Pokedex,
  },
};
</script>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>