<!-- TodoItem.vue -->
<template>
  <li :class="{ completed: todo.completed }">
    <input
      type="checkbox"
      :checked="todo.completed"
      @change="toggleTask"
    />
    <span>{{ todo.task }}</span>
    <button @click="removeTask">Hapus</button>
  </li>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    todo: Object,
    index: Number,
    removeTask: Function,
    toggleTask: Function,
  },
});
</script>

<style scoped>
/* Scoped CSS for TodoItem.vue */
li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px;
  border-bottom: 1px solid #ddd;
}

li:last-child {
  border-bottom: none;
}

li.completed span {
  text-decoration: line-through;
  color: #888;
}

li input[type="checkbox"] {
  margin-right: 10px;
}

li button {
  background-color: #dc3545;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

li button:hover {
  background-color: #c82333;
}
</style>
