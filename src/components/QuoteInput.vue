<template>
  <div class="row">
    <div class="col-xs-6 col-xs-offset-3">
      <form>
        <div class="form-group">
          <label for="quoteInput">Quote</label>
          <textarea id="quoteInput" class="form-control" v-model="quote"></textarea>
          <div class="text-center">
            <button class="btn btn-lg btn-primary" type="button" @click="addQuote">Add Quote</button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      quotes: {
        type: Array,
        required: true
      },
      max: {
        type: Number,
        required: true
      }
    },
    data() {
      return {
        quote: ''
      }
    },
    methods: {
      addQuote() {
        if (this.quote === '') {
          return 0;
        }

        if (this.quotes.length >= this.max) {
          alert('Too many quotes! Delete some before adding new ones!');
          return 0;
        }

        this.quotes.push(this.quote);
        this.quote = '';
      }
    }
  }
</script>

<style scoped>
  textarea {
    height: 100px; margin-bottom: 15px;
  }
</style>