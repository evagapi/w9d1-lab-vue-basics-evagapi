<template>
  <div
    class="flex shadow my-4 gap-4 p-4 bg-slate-50 relative overflow-hidden items-center"
  >
    <p class="absolute top-1 right-2 text-6xl italic font-bold text-slate-500">
      #{{ pokemon.id }}
    </p>
    <img :src="pokemon.imageUrl" alt="" class="bg-slate-400 rounded-full p-4" />
    <div class="flex flex-col gap-2">
      <h2 class="capitalize font-bold text-lg">{{ pokemon.name }}</h2>
      <p>
        Height: <span class="font-bold">{{ pokemon.height }}</span>
      </p>
      <p>
        Weight: <span class="font-bold">{{ pokemon.weight }}</span>
      </p>
      <ul class="flex gap-2">
        <PokemonTypeBadge v-for="t in pokemon.types" :key="t" :type="t" />
      </ul>
    </div>
  </div>
</template>

<script>
import PokemonTypeBadge from "./PokemonTypeBadge.vue";
export default {
  data() {
    return {
      types: [],
    };
  },
  props: ["pokemon"],
  components: { PokemonTypeBadge },
};
</script>

<style lang="scss" scoped></style>
