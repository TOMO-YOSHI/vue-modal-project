<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <!-- <Modal header="Sign up for the Giveaway!" text="Grab your ninja swang for half price!" /> -->
  <div v-if="showModal">
    <!-- <Modal :header='header' :text="text" theme="sale" @close="toggleModal" /> -->
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Givaway!</h1>
      <p>Grab your ninja swang for half price!</p>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <!-- Coding challenge -->
    <Modal theme="" @close="toggleModalTwo">
      <template v-slot:links>
        <a href="#">Use third party account!</a>
        <a href="#">more info</a>
      </template>
      <h1>This is a challenge!</h1>
      <p>Grab your ninja swang for good price!</p>
    </Modal>
  </div>
  <button @click="toggleModal">open modal</button>
  <button @click="toggleModalTwo">open modal two</button>
  <!-- <button @click.alt="toggleModal">open modal (alt)</button> -->
  <!-- <input type="text" ref="name">
  <button @click="handleClick">click me</button> -->
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components:{
    Modal
  },
  data() {
    return {
      title: 'My First Vue App :)',
      header: "Sign up for the Giveaway!",
      text: 'Grab your ninja swang for half price!',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
