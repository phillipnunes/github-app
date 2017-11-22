<template>
  <div class="container">
    <Card v-for="cards in 7" v-bind:key="cards"></Card>
  </div>
</template>

<script>
import Card from './components/Card'

export default {
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
