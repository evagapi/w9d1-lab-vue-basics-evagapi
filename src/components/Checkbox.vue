<template>
  <div>
    <input type="checkbox" :id="id" :name="id" v-model="value" />
    <label class="ml-2" :for="id">{{ label }}</label>
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    modelValue: Boolean,
  },
  computed: {
    value: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit("update:modelValue", value);
      },
    },
  },
  emits: ["update:modelValue"],
};
</script>
