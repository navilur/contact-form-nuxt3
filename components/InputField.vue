<template>
  <label
    class="block text-[18px] uppercase tracking-wide text-gray-700 text-xs font-bold mb-3"
    >{{ label }}</label
  >
  <input
    :value="value"
    @input="validateInput"
    :class="{ error: showError }"
    class="appearance-none block w-full bg-[#F4F8FC] text-gray-700 border border-[#E6EDF6] rounded py-3 px-4 leading-tight focus:outline-none"
  />
  <div v-if="showError" class="error-message text-[18px]">
    {{ errorMessage }}
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    value: String,
  },
  data() {
    return {
      showError: false,
      errorMessage: "This field is required.",
    };
  },
  methods: {
    validateInput(event) {
      this.$emit("input", event.target.value);
      this.showError = !this.value;
    },
  },
};
</script>

<style scoped>
.error {
  border: 1px solid red;
}
.error-message {
  color: red;
}
</style>
