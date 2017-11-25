<template>
  <div class="search">
    <p class="search__title">Busque algo no GitHub</p>
    <input class="search__input"
      v-model="search_value"
      v-on:keyup.enter="getData"
      type="search"
      id="#search"
      placeholder="Digite algo e aperte enter">
    <p class="search__results">{{ total_results }}</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      search_value: '',
      total_results: ''
    }
  },
  methods: {
    getData () {
      this.$http.get('https://api.github.com/search/repositories?q=' + this.search_value)
        .then(response => {
          return response.json()
        })
        .then(data => {
          if (data.total_count === 0) {
            this.showMessage('not_found')
          }
          var resultArray = []
          for (let key in data) {
            if (key === 'items') {
              resultArray.push(data[key])
            }
          }
          this.$emit('result', resultArray)
        })
      this.clear()
    },
    clear () {
      this.search_value = ''
      this.total_results = ''
    },
    showMessage (value) {
      if (value === 'not_found') {
        this.total_results = 'Nenhum resultado encontrado'
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '../sass/colors.scss';

  .search {
    display: flex;
    flex-flow: column;
    justify-content: center;
  }
  .search__input {
    align-self: center;
    border-radius: 25px;
    border: 1px solid $border-color;
    height: 35px;
    padding-left: 10px;
    width: 300px;
  }
  input:focus {
    outline: 0 none;
  }
  .search__title,
  .search__results {
    text-align: center;
  }
</style>
