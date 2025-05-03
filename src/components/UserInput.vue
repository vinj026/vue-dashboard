<template>
  <input type="type" id="Input" @keyup.enter="getUserInput" v-model="usrInput" />
</template>

<script setup>
import { ref, reactive } from "vue";

const usrInput = ref("");
const emit = defineEmits(["sendData"]);

function getUserInput() {
  emit("sendData", {
    task: String(usrInput.value),
    id: Number,
    checked: false,
  });
  usrInput.value = "";
}
</script>

<style scoped>
#Input {
  width: 100%;
  border: none;
  box-sizing: border-box;
  padding: 10px;
  height: 40px;
}

#Input:focus {
  border: none;
  outline: none;
}
</style>
