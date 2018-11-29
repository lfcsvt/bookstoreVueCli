<template>
  <div class="home">
    <div class="search-cart">
      <!-- <img src="../assets/logo.png" alt="The BookShop" style="width:50px;height:50px"> -->
        <p>Search your books here: 
          <input type="text" v-model="search" placeholder="Search Books">
      </p>
      <ShoppingBag/>
    </div>
    <div class="wraper"> 
         <div class="home-place">
      <div class="book-shelf" v-for="(book, index) in filteredBooks" :key="index">
          <Book v-bind:oneBook="book"/>      
      </div>
    </div> 
    </div>
  </div>
</template>

<script>
import Book from "@/components/Book.vue";
import Modal from "@/components/Modal.vue";
import ShoppingBag from "@/components/ShoppingBag.vue";
export default {
  name: 'home',
  components: {
    Book,
    Modal,
    ShoppingBag
  },
  props:['books'],

  data (){
  return {
    allBooks: [],
    hCartItems: [],
    search: ''
  }    
},
 computed: {
          filteredBooks(){
            return this.allBooks.filter((book)=> {
              return book.titulo.toLowerCase().match(this.search.toLowerCase())
            })
          }
},
created (){
  // if(!this.$route.params.allBooks){
    
    this.allBooks = this.$parent.books
  // } else {
   
  //   this.$route.params.books
  // }
}
}
</script>
<style>
.home-place {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin: 40px;

}
.book-shelf {
  margin-bottom: 20px;
}

.search-cart {
  display: flex;
  justify-content: space-around;
  width: 100%;
  height: 80px;
  padding-top: 30px;
  background-image: url(../assets/books.jpg);
  color: white;
  

}

.wraper {
  overflow: auto;
  height: 800px;
}
</style>

