<template>
  <div class="row">
    <quote v-for="(quote, index) in quotes" :quote="quote" :index="index"></quote>
  </div>
</template>

<script>
  import Quote from './Quote.vue';

  export default {
    props: {
      quotes: {
        type: Array,
        required: true
      }
    },
    components: {
      quote: Quote
    }
  }
</script>

<style scoped>
  .row {
    margin-top: 20px;
  }
</style>
