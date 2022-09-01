<template>
  <p v-if="loading">
    <span class="animate-spin inline-block">⚙️</span>
  </p>
  <button
    @click="showPrevious"
    :disabled="isDisabledPrevious"
    class="px-2 py-1 mt-4 mr-2 border-2 rounded font-bold bg-slate-100"
  >
    Previous
  </button>
  <span>{{ currentPage }} / {{ totalPages }}</span>
  <button
    @click="showNext"
    :disabled="isDisabledNext"
    class="px-2 py-1 mt-4 ml-2 border-2 rounded font-bold bg-slate-100"
  >
    Next
  </button>
  <Pokemon v-for="pokemon in pokemons" :key="pokemon.id" :pokemon="pokemon" />
</template>

<script>
import Pokemon from "./Pokemon.vue";
const STEP = 20;

export default {
  data() {
    return {
      loading: true,
      pokemons: [],
      offset: 0,
      count: 151,
    };
  },
  mounted() {
    this.fetchAPI();
  },
  methods: {
    async fetchAPI() {
      const response = await fetch(
        `https://pokeapi.co/api/v2/pokemon/?limit=${STEP}&offset=${this.offset}`
      );
      const data = await response.json();
      this.count = data.count;
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
    showNext() {
      this.offset += STEP;
      this.fetchAPI();
    },
    showPrevious() {
      this.offset -= STEP;
      this.fetchAPI();
    },
  },
  computed: {
    isDisabledPrevious() {
      return this.offset === 0;
    },
    isDisabledNext() {
      return this.offset + STEP > this.count;
    },
    currentPage() {
      return Math.floor(this.offset / STEP) + 1;
    },
    totalPages() {
      return Math.floor(this.count / STEP) + 1;
    },
  },
  components: { Pokemon },
};
</script>
