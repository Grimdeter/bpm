<template>
  <div class="columns-2 mb-10">
    <div class="flex items-center justify-center">
      <img
        src="https://images.squarespace-cdn.com/content/v1/5b4d519cf79392aa9bf1f38e/42ee5807-5259-4275-b7ff-a48a87933cb9/Cadence-Logo-Main.png"
        height="300"
        width="300"
        alt=""
      />
    </div>
    <div>
      <div
        class="mt-5 p-4 w-full text-center bg-white rounded-lg border shadow-md sm:p-8 dark:bg-gray-800 dark:border-gray-700"
      >
        <h5 class="mb-2 text-3xl font-bold text-gray-900 dark:text-white">
          What is Cadence?
        </h5>
        <p class="mb-5 text-base text-gray-500 sm:text-lg dark:text-gray-400">
          One of the ways that we can tune your walking to BPM will be my
          measuring you steps per minute (cadence)
        </p>
        <p class="mb-5 text-base text-gray-500 sm:text-lg dark:text-gray-400">
          To help you measure you cadence just click button lower and count how
          many steps you had taken.
        </p>
        <div
          class="justify-center items-center space-y-4 sm:flex sm:space-y-0 sm:space-x-4"
        >
          <div
            class="w-full sm:w-auto bg-gray-800 hover:bg-gray-700 focus:ring-4 focus:outline-none focus:ring-gray-300 text-white rounded-lg inline-flex items-center justify-center px-4 py-2.5 dark:bg-gray-700 dark:hover:bg-gray-600 dark:focus:ring-gray-700"
          >
            <div class="text-left">
              <div
                class="-mt-1 font-sans text-md font-semibold cursor-pointer"
                @click="TimerMethod"
              >
                Start timer
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      enteredCadence: null,
      cadence: null,
    };
  },
  emits: ["cadence-event"],
  watch: {
    enteredCadence(value) {
      this.cadence = value * 4;
      this.$emit("cadence-event", this.cadence);
    },
  },
  methods: {
    TimerMethod() {
      console.log(this.cadence);
      const audio = new Audio(require("../assets/bell-notification.wav"));
      setTimeout(() => {
        audio.play();
      }, 15000);
    },
  },
};
</script>
