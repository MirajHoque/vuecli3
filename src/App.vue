<template>
  <h1>{{ title }}</h1>
  <p>welcome...</p>
  <teleport to="#modals" v-if="showModal">
    <Modal  theme="" @close="toggleModal" >
      <template v-slot:links> 
        <a href="#">sign up</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for the half price</p>
    </Modal>
  </teleport>

   <teleport to="#modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo" >
      <h1>sign up for Newsletter</h1>
      <p>for updates and promo codes</p>
    </Modal>
   </teleport>

  <button @click.alt="toggleModal">Open Modal (alt)</button>
  <button @click="toggleModalTwo">Open Modal</button>
  
  
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App', //this is optional
  components: {
    Modal
  },
 data(){
   return{
     title: 'My First Vue App :)',
     showModal: false,
     showModalTwo: false
   }
 },

 methods: {
   toggleModal(){
     return this.showModal= !this.showModal;
   },
   toggleModalTwo(){
     return this.showModalTwo= !this.showModalTwo;
   }
   }
 }

</script>

<style>
#app {
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
