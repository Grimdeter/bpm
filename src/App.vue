<template>
  <div class="">
    <the-header></the-header>
    <!-- <div class="bg-gray-900">contetn</div> -->
    <the-bpm></the-bpm>
    <TheTimer />
    <TheCadence @cadence-event="setBpm" />
    <BpmInput @setBpm="setBpm" />
    <TheResults v-if="playlist !== ''" :playlist="playlist" />
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheBpm from "./components/TheBpm.vue";
import BpmInput from "./components/BpmInput.vue";
import TheTimer from "./components/TheTimer.vue";
import TheResults from "./components/TheResults.vue";
import TheCadence from "./components/TheCadence.vue";

export default {
  data() {
    return {
      cadence: null,
      bpm: null,
      playlist: "",
      linksDatabase: [
        {
          id: 0,
          BPM: 100,
          link: "https://www.youtube.com/watch?v=b7k0a5hYnSI&list=PLUF3tP5MftlHI1vA4IuB6WgO5ts00Wil1",
        },
        {
          id: 1,
          BPM: 110,
          link: "https://www.youtube.com/watch?v=5Wiio4KoGe8&list=PLzcSfO6oWDLmr9WhNDenUgxCfbqHic4YX",
        },
        {
          id: 2,
          BPM: 115,
          link: "https://www.youtube.com/watch?v=5Wiio4KoGe8&list=PLzcSfO6oWDLmr9WhNDenUgxCfbqHic4YX",
        },
        {
          id: 2,
          BPM: 120,
          link: "https://www.youtube.com/watch?v=ASXVddgxMeo&list=PLN2kbeB23nz6MH51NlydV51jhc-rUdw2p",
        },
      ],
    };
  },
  name: "App",
  components: {
    TheHeader,
    TheBpm,
    BpmInput,
    TheTimer,
    TheResults,
    TheCadence,
  },
  methods: {
    setBpm(cadence) {
      switch (cadence) {
        case 100:
          this.playlist = this.linksDatabase[0];
          break;
        case 110:
          this.playlist = this.linksDatabase[1];
          break;
        case 115:
          this.playlist = this.linksDatabase[2];
          break;
        case 120:
          this.playlist = this.linksDatabase[3];
          break;

        default:
          break;
      }
      console.log(this.playlist);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  /* color: #2c3e50; */
  /* margin-top: 60px; */
}
</style>
