<template>
  <div id="app">
    <div v-if="!dataAreIn">
      <p>loading......</p>
    </div>

    <div v-else>
       <div id="nav">
         <router-link :to="{ name: 'home', params: { allBooks: this.books }}">
            Home
          </router-link> |
    
            <router-link :to="{ name: 'bookList', params: { allBooks: this.books }}">
              Book List

            </router-link>
        </div>
     
        <router-view/>
    </div>
  </div>
</template>
<script>

export default {
  data(){
    return {
      books: [],     
      // isLoading: true
    }
  },
  components: {
 
  },
  computed:{
    dataAreIn(){
      return this.books.length > 0
    }

  },
   methods: {
     getBooks(){
       var url = "https://api.myjson.com/bins/udbm5"
       fetch(url)
      .then(response => response.json())
      .then(response => {
           this.books = response.books
          //  console.log(this.books)
          //  this.isLoading = false
      })
     }  
        },
        created(){
          this.getBooks()
        }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

</style>
