<template>
  <div class="row">
    <div class="col-xs-12">
      <div class="progress">
        <div role="progressbar" :class="progressBarClass" :aria-valuenow="quotes.length" aria-valuemin="0" :aria-valuemax="max"
             :style="progressBarStyle">
          <template v-if="quotes.length > 0">
            {{ quotes.length }} / {{ max }}
          </template>
        </div>
      </div>
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
    computed: {
      progressBarClass() {
        return {
          'progress-bar': true,
          'progress-bar-danger': (this.quotes.length === this.max),
        }
      },
      progressBarStyle() {
        return {
          width: ((this.quotes.length / this.max) * 100) + '%',
        }
      }
    },
  }
</script>

<style>

</style>