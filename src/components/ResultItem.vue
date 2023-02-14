<template>
    <p>Reaction Time - {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>
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
      this.rank = 'Very Fast speed'
    } else if (this.score < 600) {
      this.rank = 'Average Fast speed'
    } else {
      this.rank = 'slow speed......'
    }
  }
}
</script>

<style>
.rank {
  color: rgb(8, 27, 21);
  font-weight: bold;
}
</style>
