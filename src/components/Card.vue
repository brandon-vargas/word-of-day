<template>
    <div class="card-container">
        <h2>{{title}}</h2>
        <p>{{content}}</p>
    </div>
</template>
<script>
export default {
    name: 'Card',
    props: {
        title: {type: String},
        content: {type: String}
    }
}
</script>
<style scoped>
.card-container{
    /* border: solid grey 1px; */
    border-radius: 4px;
    padding: 20px;
    box-shadow: 0 3px 1px -2px rgb(0 0 0 / 20%), 0 2px 2px 0 rgb(0 0 0 / 14%), 0 1px 5px 0 rgb(0 0 0 / 12%);
}
</style>