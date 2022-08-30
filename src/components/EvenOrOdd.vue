<template>
  <span v-if="isEven" class="text-teal-700 font-bold">even</span>
  <span v-else class="text-pink-700 font-bold">odd</span>
</template>

<script>
export default {
  props: {
    number: Number,
  },
  computed: {
    isEven() {
      return this.number % 2 === 0; // iteration 3: boolean
    },
  },
};
</script>
