<template>
    <div>
        <p>Need help identifying walking cadence? Just press this <button @click="TimerMethod">BUTTON</button> and count how many steps you had taken. </p>
        <p>App will notify you when 15 seconds had passed</p>
        <p>Then enter number of steps you had taken into a field below</p>
        <input type="number" v-model="enteredCadence" name="cadence" id="cadenceInput">
        <p v-if="cadence !== null"> Your cadence is {{cadence}}</p>
    </div>
</template>

<script>
export default {
    data(){
        return {
            enteredCadence: null,
            cadence: null
        }
    },
    emits: ['cadence-event'],
    watch:{
        enteredCadence(value){
            this.cadence = value*4
            this.$emit('cadence-event', this.cadence)
        }
    },
    methods: {
        TimerMethod() {
            console.log(this.cadence)
            const audio = new Audio(require('../assets/bell-notification.wav'))
            setTimeout(() => {
                audio.play()
            }, 15000);
        }
    }
}
</script>