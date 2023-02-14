<template>
  <h1>Aqib Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Click to play</button>
  <BlockItem v-if="isPlaying" :delay="delay" @end="endGame" />
  <ResultItem v-if="showResults" :score="score" />
</template>

<script>
import BlockItem from './components/BlockItem.vue'
import ResultItem from './components/ResultItem.vue'
export default {
  name: 'App',
  components: { BlockItem, ResultItem },
  data () {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start () {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
    endGame (reactionTime) {
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
  color: #444;
  margin-top: 60px;
}
button {
  background: #0faf87;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
