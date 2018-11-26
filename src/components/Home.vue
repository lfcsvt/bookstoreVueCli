<template>
  <div class="home">
      <BookShopNavbar/>
  <div class="home-place">
      <div class="book-shelf" v-for="(book, index) in books" :key="index">
         <Book v-bind:oneBook="book"/>
    </div>
  </div>
    
  </div>
</template>

<script>
import Book from "@/components/Book.vue";
import BookShopNavbar from "@/components/BookShopNavbar.vue";

export default {
  name: 'home',
  components: {
    Book,
     BookShopNavbar
  },
  props:['books'],

  created (){
    
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

