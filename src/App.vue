<template>
  <div id="app">
    <Search v-on:getWord='getWord'/>
    <Word v-if='wordDetails.length' v-bind:wordDetails='wordDetails' />
    <h2 v-else>Please search for a word</h2>
  </div>
</template>

<script>
  import Search from './components/Search.vue'
  import Word from './components/Word.vue'
  import { APIKey } from './APIKey.js'

  export default {
    name: 'app',
    components: {
      Word,
      Search
    },
    data: () => {
      return {
        wordDetails: []
      }
    },
    methods: {
      getWord: function(word) {
        if(word) {
          fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${word}?key=${APIKey}`)
            .then(response => response.json())
            .then(wordInfo => this.wordDetails = wordInfo)      
        }
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
