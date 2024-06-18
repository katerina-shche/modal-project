<template>
  <h1>{{ title }}</h1>
  <teleport to='#modals' v-if="showModal">
  <Modal theme='sale' @close='toggleModal'>
    <template v-slot:links>
      <a href="#">sign up</a>
      <a href="##">more info</a>
    </template>
    <h1>Ninja Giveaway!</h1>
    <p>Grab your ninja swag for half prise</p>
  </Modal>
  </teleport>
  <button @click='toggleModal'>open modal</button>
  <teleport to='#modals' v-if='showModalTwo'>
  <Modal @close='toggleModalTwo'>
    <template v-slot:links>
      <a href="#">sign up too</a>
      <a href="##">more info about modal two</a>
    </template>
    <h1>Sign up for the newsletter</h1>
    <p>For updates and promo codes!</p>
  </Modal>
  </teleport>
  <button @click='toggleModalTwo'>open modal two</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    handleClick() {
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
