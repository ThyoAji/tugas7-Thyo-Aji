<!-- TodoInput.vue -->
<template>
  <div class="input-container">
    <input
      v-model="newTask"
      @keyup.enter="addTask"
      placeholder="Tambah Tugas Baru"
      class="inp"
    />
    <button @click="addTask" class="plus">Tambah</button>
  </div>
</template>

<script>
import { ref } from "vue";
import { useTodoStore } from "../store/store";

export default {
  setup() {
    const newTask = ref("");
    const todoStore = useTodoStore();

    const addTask = () => {
      if (newTask.value.trim() !== "") {
        todoStore.addTodo(newTask.value);
        newTask.value = "";
      }
    };

    return {
      newTask,
      addTask,
    };
  },
};
</script>

<style scoped>
/* Scoped CSS for TodoInput.vue */
.input-container {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
  background-color: red;
}

.inp {
  flex-grow: 1;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 16px;
}

.inp:focus {
  background-color: #a9a9a973;
}

.inp:focus::placeholder {
  color: #ffffff;
}

.plus {
  color: rgb(214, 75, 75);
  background-color: rgba(18, 19, 18, 0.42);
}

.plus:hover {
  background-color: rgba(26, 29, 27, 0.194);
}
</style>
