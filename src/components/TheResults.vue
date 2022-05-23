<template>
    <div>
        <p>Here is your  <a :href="playlist.link">perfect walking playlist</a></p>
    </div>

</template>

<script>
export default {
    props: ['playlist'],
    computed: {
        showLink(playlist) {
            return playlist.BPM
        }
    }
}
</script>