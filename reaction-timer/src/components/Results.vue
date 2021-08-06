
<template>
    <p>Reaction Time: {{score}}</p>
    <p class="rank">{{rank}}</p>
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
        if(this.score < 250 ){
            this.rank = "Ninja Fingers"
        }
        else if(this.score < 400){
            this.rank = "Rapid reflaxes"
        }
        else{
            this.rank = "Snail pace..."
        }
    }
}
</script>

<style>
    .rank {
        font-size: 1.4em;
        color: #0fea0f;
        font-weight: bold;
    }
</style>