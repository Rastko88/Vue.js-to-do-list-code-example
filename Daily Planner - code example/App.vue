<template>
  <div id="main">
    <div id="header">
      <progress-bar
        :quoteCount="quoteCount"
        :maxQuotes="maxQuotes"></progress-bar>
      <new-quote @QuoteWasCreated="addCreatedQuote"></new-quote>
    </div>
    
    <quote-grid 
      :quotes="quotes"
      @quoteWasDeleted="destroyQuote"></quote-grid>

    <h3 id="info">Info: Click on a card to delete it</h3>
    
  </div>
</template>

<script>
  import QuoteGrid from './QuoteGrid.vue';
  import NewQuote from './NewQuote.vue';
  import ProgressBar from './ProgressBar.vue';

  export default {
    data: function() {
      return {
        quotes: [],
        maxQuotes: 10,
        quoteCount: 0,
      }
    }, 
    methods: {
      addCreatedQuote(data) {
        if (data !== '') {
          if (this.quoteCount === 10) {
            alert ('Please delete some tasks first. Thank you!');
          } else {
            this.quotes.push(data);
            this.quoteCount++;
          }
          console.log(this.quoteCount);
        } 
      },
      destroyQuote(index) {
        this.quotes.splice(index, 1);
        this.quoteCount--;
      }
    },
    components: {
        'quote-grid': QuoteGrid,
        'new-quote': NewQuote,
        'progress-bar': ProgressBar,
      }    
  }
</script>

<style scoped>
  #main {
    width: 100%;
    height: 97vh;
    border-radius: 8px;
    margin: 0 auto;
    box-sizing: border-box;
    font-family: 'Raleway', sans-serif;
    background: url(images/background.jpg) no-repeat center center fixed; 
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    background-position: center;

    display: -webkit-box;
  	display: -moz-box;
  	display: -ms-flexbox;
  	display: -webkit-flex;
  	display: flex;
  
    flex-flow: column wrap;
  	-webkit-flex-flow: column wrap;
	  justify-content: space-between;
	  align-items: center;
  }
  #header {
    width: 100%;
    margin: 0;
  }
  #info {
    width: 90vw;
    padding: 10px 20px;
    border: 1px solid #FF4C4C;
    border-radius: 8px;
    text-align: left;
    color: #FF4C4C;
  }
  
  
</style>