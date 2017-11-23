<template>
  <div class="container">
    <Card></Card>
    <button @click="getData">GET</button>
  </div>
</template>

<script>
import Card from './components/Card'

export default {
  data () {
    return {
      repositories: []
    }
  },
  methods: {
    getData () {
      this.$http.get('https://api.github.com/search/repositories?q=tetris')
        .then(response => {
          return response.json()
        })
        .then(data => console.log(data))
    }
  },
  components: {
    Card
  }
}
</script>

<style>
  html {
    font-family: 'monospace';
  }
  .container {
    display: flex;
    flex-flow: row wrap;
    margin: 0 auto;
    max-width: 980px;
  }
</style>
