<template>
    <div>
        <app-quote 
            v-for="(quote, index) in quotes"
            @click.native="deleteQuote(index)"
            >{{ index + 1 }}. {{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'
    
    export default {
        props: ['quotes'],
        components: {
            'app-quote': Quote,
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteWasDeleted', index);
            }
        }
    }
    
</script>

<style scoped>

div {
    width: 98vw;
    

    display: -webkit-box;
  	display: -moz-box;
  	display: -ms-flexbox;
  	display: -webkit-flex;
  	display: flex;
  
    flex-flow: row wrap;
  	-webkit-flex-flow: row wrap;
	justify-content: flex-start;
	align-items: flex-start;
}

</style>