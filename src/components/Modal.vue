<template>
  <div>
    <b-button  class="mt-3" variant="outline-primary" @click="showModal">
      More Info
    </b-button>
    <b-modal ref="myModalRef" hide-footer :title= oneBook.titulo style="color: grey;">
      <div class="d-block" >
         
          <img :src=oneBook.portada alt="" style="width:160px;height:200px;">
           <p>language: {{oneBook.idioma}}</p>
    

      </div>
      <b-btn class="mt-3" variant="outline-success" @click="seletItems">Buy Me</b-btn>
    </b-modal>
  </div>
</template>
<script>
var arr = []
export default {
    name: 'modal',
    props:['oneBook', 'arr'],
    components: {
    
    },
    data(){
        return {
            cart: []
        }
    },
  methods: {
    showModal () {
      this.$refs.myModalRef.show()
    },
    seletItems(){
       arr.push(this.oneBook) 
        this.$parent.cartItems = arr
      console.log( this.$parent.cartItems) 
      return this.$parent.cartItems 
    }
  },
  created(){
     console.log() 
  
  }
}
</script>
<style scoped>
.a {
    text-decoration: none;
    }
 .d-block {
     color: black
 }   
</style>



