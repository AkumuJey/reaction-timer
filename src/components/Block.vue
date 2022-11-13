<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        <h1>Click Me</h1>
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTime()
        }, this.delay)
    },
    methods: {
        startTime() {
            this.timer = setInterval(() => {this.reactionTime += 10}, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit("end", this.reactionTime)
        }
    }
}
// function correctTime() {
//     currentTime = new Date()
//     document.getElementById("time").innerHTML = currentTime.toLocalTimeString()
// }
// setInterval(correctTime, 1000)
</script>

<style>
.block {
    width: 400px;
    border-radius: 20px;
    background-color: navy;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>
