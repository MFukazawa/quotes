<template>
  <div class="container">
    <!-- Either move data to App or pass props from Header up to parent and then to quote-box -->
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <br />
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid @quoteDeleted="deleteQuote" :quotes="quotes" />
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it</div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";

export default {
  data: function() {
    return {
      quotes: ['"Ayyyyyyyyyyyy lmao" - Albert Einstein'],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("You have too many quotes. Delete one to continue");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appHeader: Header,
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote
  }
};
</script>

<style>
</style>
