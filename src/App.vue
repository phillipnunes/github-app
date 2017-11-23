<template>
  <div>
    <header class="header">
      <Search></Search>
      <Button></Button>
    </header>
    <main class="main container">
      <Card></Card>
    </main>
  </div>
</template>

<script>
import Card from './components/Card'
import Search from './components/Search'
import Button from './components/Button'

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
    Card, Search, Button
  }
}
</script>

<style lang="scss">
  html {
    font-family: 'monospace';
  }
  .container {
    margin: 0 auto;
    max-width: 980px;
  }
  .header {
    background: #C9D6FF;
    background: -webkit-linear-gradient(to right, #E2E2E2, #C9D6FF);
    background: linear-gradient(to right, #E2E2E2, #C9D6FF);
    display: flex;
    height: 200px;
    justify-content: center;
  }
  .main {
    display: flex;
    flex-flow: row wrap;
  }
</style>
