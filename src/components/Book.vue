<template>
    <div class="flip-card">
  <div class="flip-card-inner">
    <div class="flip-card-front">
      <img :src=oneBook.portada alt="" style="width:300px;height:500px;">
    </div>
    <div class="flip-card-back">
      <h1>{{oneBook.titulo}}</h1> 
      <p>{{oneBook.descripcion}}</p> 
      <img :src=oneBook.detalle alt="" style="width:100px;height:100px;">
      <div class="button-div"><Modal/></div>
    </div>
  </div>
</div>
</template>

<script>
import Modal from "@/components/Modal.vue";
export default {
    name: "Book",
    props: ["oneBook"],
    components: {
      Modal
    },
    created (){
    }
}
</script>
<style scoped>
 .button-div {

   margin-top: 40px !important;

   color: white;
   border-radius: 5px;
   text-align: center;
   }
 .flip-card {
  background-color: transparent;
  width: 300px;
  height: 500px;

  perspective: 1000px; /* Remove this if you don't want the 3D effect */
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  background-color: transparent;
  color: black;
}

/* Style the back side */
.flip-card-back {
  background-color: transparent;
  color: grey;
  transform: rotateY(180deg);
}
</style>


