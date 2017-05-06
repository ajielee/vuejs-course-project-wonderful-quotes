<template>
  <div class="container">
    <app-title></app-title>
    <progress-bar></progress-bar>
    <quote-input></quote-input>
    <quotes-list></quotes-list>
    <info></info>
  </div>
</template>

<script>
  import AppTitle from './components/Title.vue';
  import ProgressBar from './components/ProgressBar.vue';
  import QuoteInput from './components/QuoteInput.vue';
  import QuotesList from './components/QuotesList.vue';
  import Info from './components/Info.vue';

  export default {
    components: {
      appTitle: AppTitle,
      progressBar: ProgressBar,
      quoteInput: QuoteInput,
      quotesList: QuotesList,
      info: Info,
    }
  }
</script>

<style>
</style>
