<template>
  <div class="output-container">
    <ul>
      <TodoItem
        v-for="(todo, index) in filteredTodos"
        :key="index"
        :todo="todo"
        :index="index"
        :removeTask="removeTask"
        :toggleTask="toggleTask"
      />
    </ul>
    <p class="incomplete-count">Tugas yang belum selesai: {{ incompleteTodosCount }}</p>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
import { computed } from "vue";
import { useTodoStore } from "../store/store";

export default {
  components: {
    TodoItem,
  },
  setup() {
    const todoStore = useTodoStore();

    const filteredTodos = computed(() => {
      if (todoStore.filter === "completed") {
        return todoStore.todos.filter((todo) => todo.completed);
      } else if (todoStore.filter === "incomplete") {
        return todoStore.todos.filter((todo) => !todo.completed);
      } else {
        return todoStore.todos;
      }
    });

    const incompleteTodosCount = computed(() => {
      return todoStore.todos.filter((todo) => !todo.completed).length;
    });

    const removeTask = (index) => {
      todoStore.removeTodo(index);
    };

    const toggleTask = (index) => {
      todoStore.toggleTodo(index);
    };

    return {
      filteredTodos,
      incompleteTodosCount,
      removeTask,
      toggleTask,
    };
  },
};
</script>

<style scoped>
.output-container {
  background-color: #f9f9f922;
  border: 1px solid #e1e1e143;
  border-radius: 8px;
  padding: 20px;
}

ul {
  list-style-type: none;
  padding: 0;
}

.incomplete-count {
  margin-top: 10px;
  font-size: 14px;
  color: #666;
}

/* Styling for TodoItem.vue (assuming it's styled separately) */
</style>
