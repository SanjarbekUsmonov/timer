<template>
 <div>
  <h1>Ninja Reaction Timer</h1>
  <button  @click="start" :disabled="isPlaying">play</button>
  <CompBlock v-if="isPlaying" :delay="delay" :click='endGame'/>
  <p>Reaction time {{score}} </p>
 </div>
</template>

<script>
import CompBlock from './components/CompBlock';


export default {
  name: 'App',
  components: { CompBlock },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null
    }
  },
  methods: {
    start(){
      this.delay  = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
