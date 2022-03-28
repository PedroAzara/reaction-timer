<template>
  <h1>Ninja Reaction Timer</h1>
  <button id="botaoIniciar" @click="start" :disabled="isPlaying">PLAY</button>
  <Block  v-if="isPlaying" :delay="delay" @end="endGame" />
 
  <Results v-if="showResults" > 
    <h1 class="result">{{ score }} ms</h1>
  </Results>
</template>

<script>

import Block from './components/Block.vue'
import Results from './components/Results.vue'
export default {
  name: 'App',
  components: 
    { Block, Results },
  data() {
      return {
        isPlaying: false,
        delay: null,
        score: null,
        showResults: false
      }
    },
  methods: {
    
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true
      console.log(this.delay)
      console.log(this.isPlaying)
      this.showResults = false

    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false  
      this.showResults = true
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
  color: #2c3e50;
  margin-top: 60px;
}

.result{
  font-size: 50px;
  padding: 20px auto;
  transition-duration: 0.1s;
  font-weight: bold;
}

.result:hover{
  transform: scale(1.20);
}

button {
  font: bold;
  font-size: 20px;
  background-color: white;
  color: #2c3e50;
  border: 2px solid #4CAF50; /* Green */
  border-radius: 100px;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  cursor: pointer;
  transition-duration: 0.3s;
  
}

#botaoIniciar:disabled {
  opacity: 0.6;
  cursor: not-allowed;

}

button:hover {
  background-color: #4CAF50; /* Green */
  color: white;
   transform: scale(1.25)
  
}


</style>
