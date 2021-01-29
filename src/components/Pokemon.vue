<template>
  <div class="pokemon">
    <h2 class="pokemon-name">{{ data.name }}</h2>
    <h3>Types:</h3>
    <ul class="pokemon-types">
      <li v-for="type in data.types" :key="type.slot">
        {{ type.type.name }}
      </li>
    </ul>
    <h3>Weight: {{ data.weight }}</h3>
    <img :src="data.sprites.front_default" />
  </div>
</template>

<script>
export default {
  name: 'Pokemon',

  props: {
    data: Object,
  },
};
</script>

<style scoped>
.pokemon {
  display: flex;
  flex-direction: column;
  align-items: center;

  min-width: 15rem;

  margin: 1rem;
  border-radius: 1.5rem;

  transition: transform ease-in-out 100ms;

  background-color: #fff;
}

.pokemon:hover {
  transform: scale(1.1);
  cursor: pointer;
}

.pokemon-name {
  text-transform: capitalize;
}

.pokemon-types li {
  text-transform: capitalize;
}
</style>
