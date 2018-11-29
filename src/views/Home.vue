<template>

  <div class="container" id="mainZone">
 
  <bookShelf :allBooks="books"></bookShelf>
  </div>
</template> 

<script>


import bookShelf from '@/components/bookShelf.vue'

  export default {
    name: 'Home',
    data() {
      return {
        books: this.$route.params.books
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