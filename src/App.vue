<template>
<h1>Ninja Reaction Timer</h1>
<button @click="start" :disabled="isPlyaing">Play</button>
<BlockComponent v-if="isPlyaing" :delay="delay" @end="endGame"/>
<ResultComponent v-if="showResult" :score="score"/>
</template>

<script>
import ResultComponent from "./components/ResultComponent.vue";
import BlockComponent from "./components/BlockComponent.vue";
export default {
  name: 'App',
  components: {
    BlockComponent , ResultComponent
  },
  data(){
    return{
        isPlyaing: false,
        delay: null,
        score: null,
        showResult: false
    }
  },
  methods:{
    start(){
     this.delay = 2000 + Math.random() * 5000
     this.isPlyaing = true;
     this.showResult = false;

    },
    endGame(reactionTime){
      this.score= reactionTime;
      this.isPlyaing = false;
      this.showResult = true;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
