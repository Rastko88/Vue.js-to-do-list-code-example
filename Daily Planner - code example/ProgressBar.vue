<template>
    
    <div id="container">
        <h2>Tasks for today - {{ quoteCount }} / {{ maxQuotes }}</h2>
        <div id="emptyBar">
            <div id="greenBar"
                :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
            </div>
        </div>
    </div>
    
</template>

<script>
    export default {
        props: ['quoteCount', 'maxQuotes']
    }
</script>

<style scoped>
#container {
    width: 100%;
    text-align: center;
    margin: 0 auto;
    font-family: 'Raleway', sans-serif;
}
#emptyBar {
    width: 95%;
    height: 40px;
    background-color: lightgrey;
    border-radius: 8px;
    border: 1px solid antiquewhite;
    margin: 0 auto;
}
#greenBar {
    background-color: #7FBF7F;
    height: 100%;
    border-radius: 8px;
    transition: width 0.6s ease-in-out;
    
}
</style>