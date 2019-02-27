<template>
  <section class='word-container'>
    <h1 class='word-name'>{{wordDetails.name}}</h1>
    <p class='word-definition'>{{wordDetails.definition}}</p>
    <h2 class='synonyms-heading'>Synonyms for <span class='word'>{{wordDetails.name}}</span></h2>
    <section class='synonym-container'>
      <Synonym v:for="synonym"/>
    </section>
    <h2 class='example-heading'>Example sentences for <span class='word'>{{wordDetails.name}}</span></h2>
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
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
