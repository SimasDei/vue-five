<template>
  <div class="container">
    <app-new-quote @quoteAdded="newQuote"/>
    <app-quote-grid :quotes="quotes"/>
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
    }
  }
};
</script>

<style>
</style>
