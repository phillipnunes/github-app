<template>
  <div class="card__container">
    <header class="card__header">
      <img class="card__image" src="https://raw.githubusercontent.com/github/explore/6c6508f34230f0ac0d49e847a326429eefbfc030/topics/vue/vue.png" alt="Imagem do repositório">
    </header>
    <main class="card__body">
      <h3 class="card__title">Vue.js</h3>
      <p class="card__text">Vue.js is a JavaScript framework for building interactive web applications.</p>
    </main>
    <footer class="card__footer">
      <p>Javascript</p>
    </footer>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style scoped lang="scss">
  .card__container {
    -moz-box-shadow: 12px 12px 22px -5px rgba(226,226,226,1);
    -webkit-box-shadow: 12px 12px 22px -5px rgba(226,226,226,1);
    border: 1px solid #CCC;
    box-shadow: 12px 12px 22px -5px rgba(226,226,226,1);
    flex: 1 0 25%;
    height: 340px;
    margin: 15px;
    min-width: 5em;
    width: 250px;
  }
  .card__header {
    background: #C9D6FF;
    background: -webkit-linear-gradient(to right, #E2E2E2, #C9D6FF);
    background: linear-gradient(to right, #E2E2E2, #C9D6FF);
    height: 80px;
    text-align: center;
  }
  .card__image {
    height: 100%;
  }
  .card__body {
    padding: 0 10px;
  }
  .card__title,
  .card__footer,
  .card__text {
    text-align: center;
  }
  .card__text {
    word-break: break-all;
  }
  .card__footer {
    border-top: 1px solid #CCC;
  }
</style>
