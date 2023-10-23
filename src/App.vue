

<template>
  <div class="game">

    <h1>Ninja reaction Timer</h1><br>
    <button :disabled="isPlaying" @click="start">Play</button><br>
    
    <Block @end="endGame" v-if="isPlaying" :delay="this.delay"/>
    <Results v-if="score" :score="this.score"/>
    
  </div>

</template>
<script >
import Results from './components/Results.vue'
import Block from './components/Block.vue'

export default{
  name:'App',
  components:{Block,Results},
  data(){
    return{
      isPlaying:false,
      delay:null,
      score:null
    }
  },
  methods:{
    start(){
      this.delay=2000+Math.random()*5000
      this.isPlaying=true;
      this.score=null;
    }
    ,endGame(reactionTime){
      this.score=reactionTime;
      this.isPlaying=false;
    }
  }
}

</script>
<style scoped>
.game{
  display:flex;
  flex-direction:column;
  margin:auto auto;
  padding:50px;
  width:100%;
  margin:0 auto;
  align-items:center;
}

</style>
