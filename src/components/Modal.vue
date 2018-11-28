<template>
  <div>
    <b-button  class="mt-3" variant="outline-primary" @click="showModal">
      More Info
    </b-button>
    <b-modal ref="myModalRef" hide-footer title="This item is available" style="color: grey;">
      <div class="d-block text-center">
        <ModalContent/>
      </div>
      <b-btn class="mt-3" variant="outline-success"><a href="http://www.amazon.de">Buy Me</a></b-btn>
    </b-modal>
  </div>
</template>
<script>
import ModalContent from "@/components/ModalContent.vue";

export default {
    name: 'modal',
    props:[],
    components: {
        ModalContent
    },
  methods: {
    showModal () {
      this.$refs.myModalRef.show()
    }
  }
}
</script>
<style scoped>
.a {
    text-decoration: none
    }
</style>



