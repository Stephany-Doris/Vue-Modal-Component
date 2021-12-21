<template>
  <button :class="{ active: modalOpen }" @click="toggleModalState">
    Open Modal
  </button>
  <teleport to="#modal-wrapper">
    <modal v-if="modalOpen" @close="toggleModalState">
      <p>Hello, am a modal window</p>
    </modal>
  </teleport>
</template>

<script>
import Modal from "./Modal.vue";
import { ref } from "vue";

export default {
  setup() {
    const modalOpen = ref(false);
    const toggleModalState = () => {
      modalOpen.value = !modalOpen.value;
    };
    return {
      modalOpen,
      toggleModalState,
    };
  },
  components: {
    Modal,
  },
};
</script>

<style scoped>
@import "./main.css";

button {
  height: 30px;
  width: fit-content;
  min-width: 150px;
  background: transparent;
  border: 1px solid black;
  border-radius: 4px;
}

.active {
  border: 3px solid #4fa2e8;
}
</style>