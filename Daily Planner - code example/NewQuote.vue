<template>
    
    <div>
        <form action="">
            <textarea name="text" id="textArea" cols="80" rows="5" autofocus v-model="quote"></textarea>
            <button @click.prevent="addQuote">Add Task</button>
        </form>
    </div>

</template>

<script>
    export default {
        data: function() {
            return {
                quote: '',
            }
        },
        methods: {
            addQuote() {
                this.$emit('QuoteWasCreated', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style scoped>
form {
    margin: 0 auto;
    padding: 0;
    font-family: 'Raleway', sans-serif;

    display: -webkit-box;
  	display: -moz-box;
  	display: -ms-flexbox;
  	display: -webkit-flex;
  	display: flex;
  
    flex-flow: row wrap;
  	-webkit-flex-flow: row wrap;
	justify-content: center;
	align-items: center;
}
textarea {
    margin-top: 12px;
    border-radius: 8px;
    border: 1px solid antiquewhite;
    background-color: rgba(77,77,77,0.8) ;
    resize: none;
    font-size: 18px;
    color: antiquewhite;
    padding: 5px;
    
    font-family: 'Montserrat', sans-serif;
}
button {
    padding: 20px;
    margin-left: 40px;
    border-radius: 8px;
    border-color: #4C0000;
    background-color: #7FBF7F;
    color: #4C0000;
    font-size: 20px;
    font-family: 'Montserrat', sans-serif;
}
</style>