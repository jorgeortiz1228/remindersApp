<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <new-quote @quoteAdded="newQuote"></new-quote>
    <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Tip : Click on a reminder to delete it !</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

export default {
  data: function() {
    return {
      quotes: [
        'Just a sample reminder .'
      ],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert('Delete a reminder before adding a new one .');
      }
      this.quotes.push(quote);
    },
    deleteQuote(i) {
      this.quotes.splice(i, 1);
    }
  },
  components: {
    'quote-grid': QuoteGrid,
    'new-quote': NewQuote,
    'app-header': Header
  }
}
</script>

<style>

</style>
