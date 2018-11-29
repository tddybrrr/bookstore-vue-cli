<template>
    <div class="container">
    <h1> {{ test }} </h1>
    <hr>
    <ul v-for="book in books">
        <li>--{{book.titulo}}</li>
    </ul>
</div>
</template>

<script>

export default {
    name: 'bookList',
    data(){
        return{
            test: "This is a book list",
            books: this.$route.params.books
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

