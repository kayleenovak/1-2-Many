<template>
  <div id="app">
    <Search v-on:getWord='getWord' />
    <Word v-if='wordDetails.name' v-bind:wordDetails='wordDetails' v-bind:synonyms='synonyms' v-on:getWord='getWord'/>
    <h2 v-else-if='loading'>{{loading}}</h2>        
    <h2 v-else-if='error'>{{error}}</h2>    
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
        wordDetails: {
          name: '',
          definition: '',
          sentence: []
        },
        synonyms: [],
        error: '',
        loading: ''
      }
    },
    methods: {
      getWord: function(word) {
          this.wordDetails.name = ''
          this.error = ''
        if(word) {
          this.loading = 'Loading...Please Wait'
          fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${word}?key=${APIKey}`)
            .then(response => response.json())
            .then(wordInfo => this.wordCleaner(wordInfo))
            .catch(err => this.error = 'Error')      
        }
      },
      wordCleaner: function(wordInfo) {
        this.loading = ''
        if (wordInfo[0].meta) {
          this.wordDetails.name = wordInfo[0].meta.id
          this.wordDetails.definition = wordInfo[0].shortdef[0]
          this.wordDetails.sentence = wordInfo[0].def[0].sseq[0][0][1].dt[1][1][0].t.split('{it}').join('').split('{/it}').join()
          this.synonyms = wordInfo[0].def[0].sseq[0][0][1].syn_list[0].map(word => word.wd)
        } else {
          this.error = 'There are no synonyms for that word, please search for another'
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
