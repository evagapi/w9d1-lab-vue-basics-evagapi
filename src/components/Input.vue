<template>
  <label class="mr-2 w-20 inline-block" :for="id">{{ label }}</label>
  <input
    v-model="value"
    :name="id"
    :placeholder="placeholder"
    :id="id"
    class="px-4 py-2 mb-2 w-80 bg-green-50 border-green-200 border-2 rounded"
  />
</template>

<script>
export default {
  props: {
    modelValue: String,
    type: { type: String, required: true },
    id: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    placeholder: {
      type: String,
      required: true,
    },
  },
  emits: ["update:modelValue"],
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
};
</script>
