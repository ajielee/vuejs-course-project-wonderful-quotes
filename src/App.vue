<template>
  <div class="container">
    <app-title></app-title>
    <progress-bar :quotes="quotes" :max="max"></progress-bar>
    <quote-input :quotes="quotes" :max="max"></quote-input>
    <quotes-list :quotes="quotes"></quotes-list>
    <info></info>
  </div>
</template>

<script>
  import AppTitle from './components/Title.vue';
  import ProgressBar from './components/ProgressBar.vue';
  import QuoteInput from './components/QuoteInput.vue';
  import QuotesList from './components/QuotesList.vue';
  import Info from './components/Info.vue';
  import {bus} from './main.js';

  export default {
    data() {
      return {
        quotes: [],
        max: 10
      }
    },
    components: {
      appTitle: AppTitle,
      progressBar: ProgressBar,
      quoteInput: QuoteInput,
      quotesList: QuotesList,
      info: Info,
    },
    created() {
      bus.$on('deleteQuote', function (index) {
        this.quotes.splice(index, 1);
      }.bind(this));
    }
  }
</script>
