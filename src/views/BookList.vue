<template>
    <table>
        <thead>
            <th>Book Tittle</th>
            <th>Book Description</th>
             <th>Book Language</th>
        </thead>
        <tbody>
            <tr v-for="book in allBooks">
                <td>{{book.titulo}}</td>
                 <td>{{book.descripcion}}</td>
                 <td>{{book.idioma}}</td>
            </tr>
        </tbody>
    </table>
</template>
<script>
export default {
    name: "bookList",

      data (){
  return {
    allBooks: this.$route.params.allBooks
  }    
}
}
</script>
<style scoped>
table, th, td {
    border: 1px solid black;
    margin: 30px;
    font-weight: 30px;
}
</style>

