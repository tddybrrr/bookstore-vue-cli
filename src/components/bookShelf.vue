<template>
    <div class="container" id="bookShelf">
        <input type="text" placeholder="Search for a book..." v-model="searched">
        <div class="row d-flex flex-flow justify-content-between">
            <div v-for="(oneBook, index) in filteredBooks" :key="index">
                <aBook :bookFromShelf="oneBook"></aBook>
            </div>
        </div>
    </div>
</template>

<script>
    import aBook from '@/components/aBook.vue'
    export default {
        name: "bookShelf",
        components: {
            aBook
        },
        props:['myBooksFromHome'],
        data() {
            return {
                searched: '',
                test: this.myBooksFromHome
            }
        },
        computed:{
            filteredBooks(){
                return this.test.filter(oneBook => oneBook.titulo.toUpperCase().includes(this.searched.toUpperCase())|| oneBook.descripcion.toUpperCase().includes(this.searched.toUpperCase()));
            }
        }
    }
    
</script>

<style scoped>
    input {
        text-align: center;
        display: block;
        margin: 25px auto;
    }
</style>