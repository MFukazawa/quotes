<template>
  <div class="container mt-3">
    <div class="row">
      <app-quote
        :key="quote.index"
        v-for="quote in quotes"
        @click.native="deleteQuote(index)"
      >
        {{ quote }}
      </app-quote>
    </div>
  </div>
</template>

<script>
import Quote from "./Quote.vue";

export default {
  props: ["quotes"],
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  },
  components: {
    appQuote: Quote
  }
};
</script>

<style>
</style>