<template>
    <div class="results">
        <p>Reaction Time is: {{ score }} ms</p>
        <p class="rank">{{ rank }}</p>
    </div>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if(this.score < 250) {
            this.rank = "Goat!"
        } else if(this.score < 500) {
            this.rank = "Fighter!"
        } else {
            this.rank = "You tried Buddy!"
        }
}}
</script>

<style>
.results {
    width: 400px;
    border-radius: 20px;
    background-color: lightblue;
    color: black;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
.rank {
    color: black;
    font-weight: bold;
    font-size: 1.5em;
}
</style>
