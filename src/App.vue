<template>
  <h1> {{title}}</h1>
  <teleport to='.modals' v-if="showModal">
  <Modal  theme='sale' @close="toggleModal">
    <template v-slot:links>
      <a href="#">Click it click it real good</a>
      <a href="#">what is pew</a>
    </template>
    <h1>PEW PEW?</h1>
    <p>pewpewpepwppewpewpewpewpewpewpepwpew</p>
  </Modal>
  </teleport>

  <teleport to='.modals' v-if="showModaltwo">
  <Modal   @close="toggleModaltwo">
    
    <h1>no PEW PEW?</h1>
    <p>Going to go pew</p>
  </Modal>
  </teleport>
  <button @click="toggleModal">Click me Baby one more time </button>
  <button @click="toggleModaltwo">Click me Baby one more time 2 </button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components: {Modal},
 data() {
   return{
     showModal: false,
     showModaltwo: false
     }
 },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModaltwo() {
      this.showModaltwo = !this.showModaltwo
    }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
