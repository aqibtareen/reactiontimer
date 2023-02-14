<template>
    <p>Reaction Time - {{ score }} ms</p>
    <p class="rank">{{ rank }} </p>
    <p class="rank">Kindly click on reload to get accurate results</p>
</template>

<script>
export default {
  props: ['score'],
  data () {
    return {
      rank: null
    }
  },
  mounted () {
    if (this.score < 400) {
      this.rank = 'Very Fast Speed'
    } else if (this.score < 600) {
      this.rank = 'Average Fast Speed'
    } else if (this.score < 1000) {
      this.rank = 'Slow Speed......'
    } else {
      this.rank = 'Out Of Time'
    }
  }
}
</script>

<style>
.rank {
  font-size: 1.4em;
  color: green;
  font-weight: bold;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
</style>
