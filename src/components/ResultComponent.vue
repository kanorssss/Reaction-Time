<template>
    <p>Reaction time - {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data(){
        return{
            rank:null,
        }
    },
    mounted(){
        if (this.score < 250){
            this.rank = 'Ninja Fingers'
        }else if(this.score < 400){
            this.rank = 'Rapid Reflexis'
        }else {
            this.rank = 'Snail Pace'
        }
    }
}
</script>

<style>
.rank {
    font-size: 1.4em;
    color:aqua;
    font-weight: bold ;
}
</style>