<template>
  <p v-if="loading">
    <span class="animate-spin inline-block">⚙️</span>
  </p>
  <Pokemon v-for="pokemon in pokemons" :key="pokemon.id" :pokemon="pokemon" />
</template>

<script>
import Pokemon from "./Pokemon.vue";
export default {
  data() {
    return {
      loading: true,
      pokemons: [],
    };
  },
  mounted() {
    this.fetchAPI();
  },
  methods: {
    async fetchAPI() {
      const response = await fetch("https://pokeapi.co/api/v2/pokemon/");
      const data = await response.json();
      const pokemons = await Promise.all(
        data.results.map((pokemon) => {
          return fetch(pokemon.url).then((response) => response.json());
        })
      );
      this.pokemons = pokemons.map(
        ({ id, name, height, weight, sprites, types }) => ({
          id,
          name,
          height,
          weight,
          imageUrl: sprites.front_default,
          types: types.map((type) => type.type.name),
        })
      );
      this.loading = false;
    },
  },
  components: { Pokemon },
};
</script>
