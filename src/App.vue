<template>
  <div id="app">
    <Navbar :currentPage="currentPage" :navigate="navigatePage" />
    <div class="todo-container">
      <h1>Daftarkan List Anda Sekarang</h1>
      <div v-if="currentPage === 'home'">
        <div class="input-container">
          <input
            v-model="newTask"
            @keyup.enter="addTask"
            placeholder="Tambah Tugas Baru"
            class="inp"
          />
          <button @click="addTask" class="plus">Tambah</button>
        </div>
        <div class="output-container">
          <p class="incomplete-count">Tugas yang belum selesai: {{ incompleteTodosCount }}</p>
          <ul>
            <li v-for="(todo, index) in filteredTodos" :key="index" :class="{ completed: todo.completed }">
              <input type="checkbox" :checked="todo.completed" @change="toggleTask(index)" />
              <span>{{ todo.task }}</span>
              <button @click="removeTask(index)">Hapus</button>
            </li>
          </ul>
          
        </div>
      </div>
      <div v-else-if="currentPage === 'about'">
        <About />
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import About from './views/About.vue';
import { ref, computed } from 'vue';
import { useTodoStore } from './store/store';

export default {
  name: 'App',
  components: {
    Navbar,
    About,
  },
  setup() {
    const newTask = ref('');
    const todoStore = useTodoStore();

    const addTask = () => {
      if (newTask.value.trim() !== '') {
        todoStore.addTodo(newTask.value);
        newTask.value = '';
      }
    };

    const removeTask = (index) => {
      todoStore.removeTodo(index);
    };

    const toggleTask = (index) => {
      todoStore.toggleTodo(index);
    };

    const filteredTodos = computed(() => {
      return todoStore.todos;
    });

    const incompleteTodosCount = computed(() => {
      return todoStore.todos.filter((todo) => !todo.completed).length;
    });

    const currentPage = ref('home');

    const navigatePage = (page) => {
      currentPage.value = page;
    };

    return {
      newTask,
      filteredTodos,
      incompleteTodosCount,
      addTask,
      removeTask,
      toggleTask,
      currentPage,
      navigatePage,
    };
  },
};
</script>

<style scoped>


.todo-container {
  margin-top: 20px;
  background-color: rgba(249, 246, 246, 0);
}

h1 {
  font-size: 24px;
  margin-bottom: 20px;
  color: black;
}

.input-container {
  display: flex;
  margin-bottom: 10px;
  background-color: rgba(255, 255, 255, 0);
}

.inp {
  flex: 1;
  padding: 10px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.plus {
  background-color: #49b94f;
  color: white;
  border: none;
  padding: 10px 20px;
  margin-left: 10px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.plus:hover {
  background-color: #45a049;
}

.output-container {
  background-color: rgba(255, 255, 255, 0);
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 4px;
  max-height: 180px; 
  overflow-y: auto;  
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

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
  color: red;
}

li input[type='checkbox'] {
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

.incomplete-count {
  margin-top: 10px;
  font-size: 14px;
  color: black;
}


</style>
