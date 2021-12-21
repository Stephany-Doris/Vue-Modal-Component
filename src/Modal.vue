<template>
  <div class="modal-wrapper">
    <div class="modal">
      <slot></slot>
      <button @click="$emit(`close`)">Dismiss</button>
    </div>
  </div>
</template>

<script>
export default {
  emits: ["close"],
};
</script>

<style scoped>
@import "./main.css";

.modal-wrapper {
  top: 0;
  background-color: rgba(0, 0, 0, 0.7);
  left: 0;
  width: 100vw;
  height: 100vh;
  position: absolute;
}

.modal {
  margin: auto;
  padding: 1em;
  font-size: 20px;
  height: 250px;
  width: 500px;
  background-color: white;
  z-index: 100001;
  position: absolute;
  top: 25%;
  left: 25%;
}
::v-slotted(p) {
  font-style: italic;
}

button {
  height: 30px;
  width: 120px;
  background-color: #dcf7ff;
  border: 2px solid #187894;
  border-radius: 4px;
}
</style>
