<template>
  <div :class="backgroundColor">
    <button
      @click="toggle"
      class="px-2 py-1 border-2 m-10 rounded font-bold bg-slate-100"
    >
      Click Me! I'm the iteration 5 🙋
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
    };
  },
  methods: {
    toggle() {
      this.isActive = !this.isActive;
    },
  },
  computed: {
    backgroundColor() {
      return this.isActive ? "on" : "off";
    },
  },
};
</script>

<style>
.on {
  @apply bg-teal-500;
}

.off {
  @apply bg-pink-600;
}
</style>
