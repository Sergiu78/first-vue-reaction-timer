<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="name" />
  <button @click="handleClick">Click Me</button>
  <dir v-if="showModal">
    <Modal :header="header" :text="text" theme="sale"/>
  </dir>
  <button @click="showToggle">Open modal</button>
</template>

<script>

import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components: {Modal},
  data() {
    return {
      title: 'Hello First Vue',
      header: "Sign up for more information",
      text: "Some text about our products",
      showModal: false,
    }
  },
  methods: {
    handleClick() {
      this.$refs.name.focus()
    },
    showToggle() {
      this.showModal = !this.showModal
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
</style>
