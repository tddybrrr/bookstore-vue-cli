<template>
    <div class="container">
        <input type="text" placeholder="Search for a book..." v-model="searched">
        <div class="row d-flex flex-flow justify-content-between">
            <div v-for="book in filteredBooks">
                <aBook :title="book.titulo" :about="book.descripcion" :coverArt="book.portada" :coverArtDetail="book.detalle" :showStatus="status"></aBook>
            </div>
        </div>
    </div>
</template>

<script>
    import aBook from '@/components/aBook.vue'
    export default {
        props: ['allBooks'],
        components: {
            aBook
        },
        data() {
            return {
                searched: '',
                status: false
            }
        },
        computed:{
            filteredBooks(){
                return this.allBooks.filter(book => book.titulo.toUpperCase().includes(this.searched.toUpperCase())|| book.descripcion.toUpperCase().includes(this.searched.toUpperCase()));
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