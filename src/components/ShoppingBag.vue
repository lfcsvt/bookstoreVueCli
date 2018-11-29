<template>
<div>
    <b-button variant="primary" @click="showModal">
      My Cart
    </b-button>
    <b-modal ref="myModalRef" hide-footer title="Your cart" style="color: black;">
      <div class="d-block text-center">
        <table>
        <thead>
            <th>Item</th>
            <th>Quantity</th>
            <th>Price</th>
        </thead>
        <tbody>
            <tr>
                <td></td>
                <td></td>
                <td></td>
            </tr>
        </tbody>
    </table>
      </div>
      <b-btn class="mt-3" variant="outline-success" block @click="hideModal">To Checkout</b-btn>
    </b-modal>
  </div>
</template>
<script>
export default {
    name: 'shoppingBag',
    data(){
        return {
            cartItems: []
        }
    },
      methods: {
    showModal () {
      this.$refs.myModalRef.show()
    },
    hideModal () {
      this.$refs.myModalRef.hide()
    }
  },
  created(){
    
  }
}
</script>
<style scoped>
table, th, td {
    border: 1px solid black;
    margin: 30px;
    font-weight: 30px;
    color: black;
}
</style>


