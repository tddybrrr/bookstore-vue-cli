<template>
    <div class="container" id="bookShelf">
        <input type="text" placeholder="Search for a book..." v-model="searched">
        <div class="row d-flex flex-flow justify-content-between">
            <div v-for="(book, index) in this.$root.allBooks" :key="index">
                 <p>{{book.titulo}}</p>
                <!-- <aBook :title="book.titulo" :about="book.descripcion" :coverArt="book.portada" :coverArtDetail="book.detalle" :showStatus="status"></aBook> -->
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
        data() {
            return {
                searched: '',
                status: false,
                shmeow: this.$parent.allBooks
            }
        },
        // computed:{
        //     filteredBooks(){
        //         return this.$parent.allBooks.filter(oneBook => oneBook.titulo.toUpperCase().includes(this.searched.toUpperCase())|| oneBook.descripcion.toUpperCase().includes(this.searched.toUpperCase()));
        //     }
        // },
        created: function(){
            console.log(this.$root.allbooks)
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