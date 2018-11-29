<template>
  <div id="app" class="container">
    <div id = "navigation" class="navBar sticky-top">
      <nav class="navbar navbar-expand-lg">
        <div class="collapse navbar-collapse d-flex justify-content-between" id="navbarSupportedContent">
          <div id="links">
            <router-link :to="{ name: 'Home', params: { books: this.allBooks } }"> Home</router-link> |||
            <router-link :to="{ name: 'bookList', params: { books: this.allBooks } }"> Book List</router-link>
          </div>
          <h2 id="storeName" class="text-center">Crooked Pages Bookstore</h2>
          <a class="navbar-brand" href=""><img id="logo" src="@/assets/book-logo.png" alt='logo' /></a>
        </div>
      </nav>
    </div>
    <router-view />
  </div>
</template>

<script>


export default {
  data(){
    return{
      allBooks:[]
    }
  },
  created: function () {
            console.log("maybe this?")
            fetch('https://api.myjson.com/bins/udbm5')
                .then((response) => {
                    return response.json();
                })
                .then((data) =>{
                this.allBooks = data.books;
                });
        }
}
</script>

<style>
  #navigation {
    background-color: black;
    border-radius: 10px;
    margin-top: 30px;
    margin-bottom: 50px;
    text-align: center;
  }
  a {
    color: white;
    font-family: Product Sans;
  }

  a:hover {
    color: grey;
  }

  #logo {
    width: 60px;
    height: 60px;
  }

  input {
    border-radius: 10px;
    border-style: solid;
  }
  #storeName {
    color: dimgrey;
    letter-spacing: 2.5px;
    font-family: Product Sans;
  }
  
</style>