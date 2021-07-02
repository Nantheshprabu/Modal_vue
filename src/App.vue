<template>
  <h1>{{ title }}</h1>
  <p>Welcome!!</p>
  <div v-if="showModal">
    <Modal :header="header" theame="sale" @closeing="toggleModal">
      <template v-slot:links>
        <a href="www.amazon.in">amazon</a>
      </template>
      <h1>Giveaway Offer</h1>
    </Modal>
  </div>

  <button @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  components: { Modal },
  data() {
    return {
      title: "My first Vue App",
      header: "Sale is here",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
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
