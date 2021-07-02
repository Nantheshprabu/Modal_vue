<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theame === 'sale' }">
      <slot></slot>
      <div>
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theame"],

  methods: {
    closeModal() {
      this.$emit("closeing");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal.sale {
  background: red;
  color: white;
}
</style>