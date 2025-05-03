<script setup>
import MyDate from "./MyDate.vue";
import UserInput from "./UserInput.vue";
import TodoItem from "./TodoItem.vue";
import { onMounted, reactive, watch } from "vue";

const ToDo = reactive([]);

onMounted(() => {
  const savedTodo = localStorage.getItem("ToDo");
  if (savedTodo) {
    const jToDo = JSON.parse(savedTodo);
    console.log(jToDo);
    jToDo.forEach((task) => {
      ToDo.push(task);
    });
  }
});

function usrInputval(msg) {
  msg.id = ToDo.length + 1;
  ToDo.push(msg);
}

watch(ToDo, (newVal) => {
  localStorage.setItem("ToDo", JSON.stringify(newVal));
});

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
