<template>
  <div class="text-center mb-6 mx-auto w-3/6">
    <p>
      Here is your
      <a :href="playlist.link" class="hover:underline"
        >perfect walking playlist</a
      >
    </p>
  </div>
</template>

<script>
export default {
  props: ["playlist"],
  computed: {
    showLink(playlist) {
      return playlist.BPM;
    },
  },
};
</script>
