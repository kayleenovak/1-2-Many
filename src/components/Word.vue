<template>
  <section class='word-container'>
    <h1 class='word-name'>{{word[0].meta.id}}</h1>
    <p class='word-definition'>{{word[0].shortdef[0]}}</p>
    <h2 class='synonyms-heading'>Synonyms for <span class='word'>{{word[0].meta.id}}</span></h2>
    <section class='synonym-container'>
      <Synonym />
      <Synonym />
      <Synonym />
      <Synonym />
    </section>
    <h2 class='example-heading'>Example sentences for <span class='word'>{{word[0].meta.id}}</span></h2>
    <p class='example-sentence'>{{word[0].def[0].sseq[0][0][1].dt[1][1][0].t}}</p>
  </section>
</template>

<script>
import Synonym from './Synonym.vue'

export default {
  name: 'Word',
  components: {
    Synonym
  },
  props: ['word']
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
