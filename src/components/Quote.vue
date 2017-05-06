<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default" @click="deleteQuote">
      <div class="panel-body">
        {{ quote }}
      </div>
    </div>
  </div>
</template>

<script>
  import { bus } from './../main.js';

  export default {
    props: {
      quote: {
        type: String,
        required: true
      },
      index: {
        type: Number,
        required: true
      }
    },
    methods: {
      deleteQuote() {
        bus.$emit('deleteQuote', this.index);
      }
    }
  }
</script>

<style scoped>
  .panel {
    cursor: pointer;
  }

  .panel:hover {
    background: #ff9999;
  }

  .panel-body {
    font-family: 'Arizonia';
    font-size: 25px;
  }
</style>
