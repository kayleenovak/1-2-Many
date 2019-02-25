<template>
  <div id="app">
    <Search />
    <Word v-bind:word='word' />
  </div>
</template>

<script>
import Search from './components/Search.vue'
import Word from './components/Word.vue'

export default {
  name: 'app',
  components: {
    Word,
    Search
  },
  data: () => {
    return {
      word: []
    }
  },
  methods: {
    getWord: function() {
      fetch('https://www.dictionaryapi.com/api/v3/references/thesaurus/json/umpire?key=d2b1b340-d60a-4dd8-a962-057fe37f2dd8')
        .then(response => response.json())
        .then(wordInfo => this.word = wordInfo)      
    }
  },
  beforeMount() {
    this.getWord()
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: grid;
  grid-template-columns: 450px 1fr;
  height: 100%;
}

html {
  height: 100%;
  padding: none;
  margin: 0;
}

body {
  height: 100%;
  margin: 0;
}
</style>
