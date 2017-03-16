<template>
    
        <div id="card">
            <slot></slot>
        </div>
    
</template>

<script>
    export default {
        data: function() {
            return {
                quote: '',
                attachDeleteClass: true,
            }
        },
    }
</script>

<style scoped>
#card { 
    width: 22%;
    margin: 5px;
    padding: 8px 12px;
    border: 1px solid antiquewhite;
    background-color: rgba(77,77,77,0.8) ;
    border-radius: 8px;
    color: antiquewhite;
    font-size: 20px;
    cursor: pointer;
}

#card:hover {
    background-color: #7FBF7F;
}
.delete-class {
    display: none;
}

</style>

