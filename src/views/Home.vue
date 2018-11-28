<template>
  <div class="home">
    <p>Search your books here: 
      <input type="text" v-model="search" placeholder="Search Books">
    </p>
          
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
    allBooks: [],
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
  //   console.log('hi')
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
  justify-content: space-around;
  margin: 40px;
}
.book-shelf {
  margin-bottom: 20px;
}
</style>

