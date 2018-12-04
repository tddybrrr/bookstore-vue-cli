<template>
    <div class="container" id="mainZone">
      <bookShelf :myBooksFromHome="this.myBooks"/>
    </div>
</template> 

<script>


import bookShelf from '@/components/bookShelf.vue'

  export default {
    name: 'Home',
    data(){
      return{
        myBooks: this.$parent.allBooks
      }
    },
    components: {
      bookShelf
    }
  }
</script>

<style>
#image{
width: 50%;
height: 50%;
}
</style>