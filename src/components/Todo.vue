<script setup>
import MyDate from "./MyDate.vue";
import UserInput from "./UserInput.vue";
import TodoItem from "./TodoItem.vue";
import { reactive } from "vue";

const ToDo = reactive([]);

function usrInputval(msg) {
  msg.id = ToDo.length + 1;
  ToDo.push(msg);
}

function deleteTask(id) {
  console.log(`hapus id ${id}`);
  ToDo.shift(id - 1);
  console.log(`hapus ${id} selesai`);
}
</script>

<template>
  <div id="ContainerTodo">
    <MyDate />
    <UserInput @sendData="usrInputval" />
    <TodoItem @sendDeletedTask="deleteTask" :todoData="ToDo" />
  </div>
</template>

<style scoped>
#ContainerTodo {
  display: flex;
  flex-direction: column;
  padding: 20px;
  gap: 16px;
  background-color: #1e1e1e;
  width: 20rem;
  height: 30rem;

}
</style>
