<template>
  <div class="mb-6 mx-auto w-3/6">
    <p>Then enter number of steps you had taken into a field below</p>
    <div>
      <label
        for="default-input"
        class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300"
        >Cadence input</label
      >
      <input
        type="text"
        id="default-input"
        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
        v-model="enteredCadence"
      />
    </div>
    <p class="mb-6 mt-5" v-if="realCadence !== null">
      Your cadence is {{ realCadence }} steps per minute
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      enteredCadence: null,
      realCadence: null,
    };
  },
  emits: ["cadence-event"],
  watch: {
    enteredCadence() {
      this.realCadence = this.enteredCadence * 4;
      this.$emit("cadence-event", this.realCadence);
      console.log("hi");
    },
  },
};
</script>
