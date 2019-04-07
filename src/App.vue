<template>
  <div class="container">
    <app-new-quote @quoteAdded="newQuote"/>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"/>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alet alert-info">Info: Click on a Quote to delete</div>
      </div>
    </div>
  </div>
</template>

<script>
import appQuoteGrid from "./components/QuoteGrid.vue";
import appNewQuote from "./components/NewQuote.vue";
export default {
  data: function() {
    return {
      maxQuotes: 10,
      quotes: ["Smart fellow, he felt smart"]
    };
  },
  components: {
    appQuoteGrid,
    appNewQuote
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
</style>
