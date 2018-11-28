<template>
    <div class="modal-content">
        <h3>This item is elegible for:</h3>
        <img src="../assets/free-shipping-new.png" alt="" style="width:100px;height:100px;">
    </div>
</template>
<script>
export default {
    name: 'modalContent',
    props:['modalContent'],
    methods: {
     
    }
}
</script>
<style scoped>
.modal-content {
    height: 250px;
    width: 250px;
    color: black;
}
img {
    margin-left: 80px;
    margin-top: 60px;
}
</style>

