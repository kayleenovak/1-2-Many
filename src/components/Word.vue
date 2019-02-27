<template>
  <section class='word-container'>
    <h1 class='word-name'>{{wordDetails.name}}</h1>
    <p class='word-definition'>{{wordDetails.definition}}</p>
    <h2 class='synonyms-heading'>Synonyms for <span class='word'>{{wordDetails.name}}</span></h2>
    <section class='synonym-container'>
      <Synonym v-bind:synonym='synonym' v-on:updateWord='updateWord' v-for="synonym in synonyms"/>
    </section>
    <h2 class='example-heading'>Example sentence for <span class='word'>{{wordDetails.name}}</span></h2>
    <p class='example-sentence'>{{wordDetails.sentence}}</p>
  </section>
</template>

<script>
  import Synonym from './Synonym.vue'

  export default {
    name: 'Word',
    components: {
      Synonym
    },
    props: ['wordDetails', 'synonyms'],
    methods: {
      updateWord: function(word) {
        this.$emit('getWord', word)
      }
    }
  }
</script>

<style scoped>
  .word-container {
    text-align: left;
    margin-left: 40px;
  }

  .word-name {
    font-size: 40px;
    font-weight: bold;
    margin-bottom: 7px;
  }

  .word-definition {
    margin-top: 0;
    color: gray;
  }

  .synonyms-heading,
  .example-heading {
    font-size: 30px;
  }

  .synonym-container {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .word {
    color: gray;
    text-decoration: underline;
  }
</style>
