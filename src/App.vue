<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start">play</button>
  <CompBlock v-if="isPlaying"/>
</template>

<script>
import CompBlock from './components/CompBlock';


export default {
  name: 'App',
  components: { CompBlock },
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start(){
      this.delay  = 2000 + Math.random() * 5000
      this.isPlaying = true
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
