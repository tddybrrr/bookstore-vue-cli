<template>
    <div class="container">
    <h1> {{ test }} </h1>
    <hr>
    <div id = "bookList">
    <ul v-for="(book, index) in this.$parent.allBooks" :key="index">
        <li>--{{book.titulo}}</li>
    </ul>
    </div>
</div>
</template>

<script>

export default {
    name: 'bookList',
    data(){
        return{
            test: "This is a book list"
        }
    }
}
</script>

<style <style scoped>

h1{
    color: grey;
    text-align: center;
}
li{
    list-style-type: none;
    text-align: center;
}
</style>

