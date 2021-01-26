<template>
  <div class="row">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quotes @quoteAdd="NewQ"></app-new-quotes>
    <app-quoetes
      v-bind:quotes="quotes"
      @quoteDeleted="deleteQuote"
    ></app-quoetes>
    <div class="row">
      <div class="col-sm-12 text center">
        <div class="alert alert-info text-center" >
          Info: Click on a Quote to delete it !
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuotesGrid from "./components/QuotesGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data: function () {
    return {
      maxQuotes: 10,
      quotes: ["Test text for quote"],
    };
  },
  methods: {
    NewQ(quote) {

      
      if(this.quotes.length >= this.maxQuotes){
         return alert("Please, Delete Quotes First")
      }
      if (quote != "") {
        this.quotes.push(quote);
      }
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    },
  },
  components: {
    appQuoetes: QuotesGrid,
    appNewQuotes: NewQuote,
    appHeader: Header,
  },
};
</script>

<style>
body{
   margin-left: 5%;
}
</style>
