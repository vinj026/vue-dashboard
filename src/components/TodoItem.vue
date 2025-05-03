<template>
  <div id="todoItemContainer">
    <ul>
      <li v-for="task in props.todoData" :key="task.id">
        <div class="taskNcheck">
          <input type="checkbox" v-model="task.checked" @change="isChecked(task)" />
          <p :class="{ complete: task.checked === true }">
            {{ task.task }}
          </p>
        </div>
        <button @click="() => emit('sendDeletedTask', task.id)">
          <Trash size="16" />
        </button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, onMounted, watch } from "vue";
import { Trash } from "lucide-vue-next";
import Todo from "./Todo.vue";
const props = defineProps({
  todoData: {
    type: Array,
  },
});

const isChecked = (task) => {
  console.log(task);
};

const emit = defineEmits(["sendDeletedTask"]);
</script>

<style scoped>
#todoItemContainer {
  display: flex;
  height: 100%;
  overflow: scroll;
  padding: 0 10px 0 0;
}

ul {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  width: 100%;
}

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  align-content: center;
  width: 100%;

  list-style: none;
}

button {
  box-sizing: border-box;
  padding: 0;
  width: 30px;
  height: 30px;
}

.taskNcheck {
  display: flex;
  width: 100%;
  gap: 15px;
}

.complete {
  text-decoration: line-through;
}
</style>
