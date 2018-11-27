<template>
  <div class="home">
        <!-- <div>
          <nav class="navbar navbar-light bg-light top">
        <a class="navbar-brand">
            <img src="" width="50" height="50" alt="">
            The BookShop
        </a>   -->
<p>Search your books here: <input type="text" v-model="search" placeholder="Search Books">
     </p>
          
   
    <!-- </nav>
    </div> -->
  <div class="home-place">
      <div class="book-shelf" v-for="(book, index) in filteredBooks" :key="index">
         <Book v-bind:oneBook="book"/>
    </div>
  </div>
    
  </div>
</template>

<script>
import Book from "@/components/Book.vue";

export default {
  name: 'home',
  components: {
    Book
  },
  props:['books'],

  data (){
  return {
    search: ''
  }    
},
 computed: {
          filteredBooks(){
            return this.books.filter((book)=> {
              return book.titulo && book.descripcion.toLowerCase().match(this.search.toLowerCase())
            })
          }
        }
}
</script>
<style>
.home-place {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin: 40px;
}
.book-shelf {
  margin-bottom: 20px;
}
</style>

