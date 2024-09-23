<template>
  <div class="container">
    <div class="add-container">
      <img alt="Vue logo" src="../assets/logo.png" class="logo" />
      <h1>Todo's List!</h1>
      <p>To start, add items to your list.</p>
      <!-- <div class="todo-bar">
        <input
         v-model="data.newTodoName" 
         @keyup.enter="addTodo" 
         placeholder="Add a Todo" 
         type="text" 
         minlength="2"
         maxlength="250"
        />
        <button @click="addTodo(index)" class="add-btn">
          <svg width="40px" height="40px" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M6 12H18M12 6V18" stroke="#FFFFFF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
          </svg>
        </button>
      </div> -->
    </div>

    <div class="list-container">
      <h2 v-if="todosCount >= 1">You have {{ todosCount }} Todos!</h2>
      <h2 v-else>Add your Todo's!</h2>

      <div class="todo-bar">
        <input
         v-model="data.newTodoName" 
         @keyup.enter="addTodo" 
         placeholder="Add a Todo" 
         type="text" 
         minlength="2"
         maxlength="250"
        />
        <button @click="addTodo(index)" class="add-btn">
          <svg width="40px" height="40px" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M6 12H18M12 6V18" stroke="#FFFFFF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
          </svg>
        </button>
      </div>

      <ul>
        <li v-for="(todo, index) in data.todos" :key="todo.id">
          <span>· </span>
          <span>{{ todo.name }}</span>
          <button @click="deleteTodo(index)" class="remove-btn">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
              <path
                d="M135.2 17.7C140.6 6.8 151.7 0 163.8 0L284.2 0c12.1 0 23.2 6.8 28.6 17.7L320 32l96 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 96C14.3 96 0 81.7 0 64S14.3 32 32 32l96 0 7.2-14.3zM32 128l384 0 0 320c0 35.3-28.7 64-64 64L96 512c-35.3 0-64-28.7-64-64l0-320zm96 64c-8.8 0-16 7.2-16 16l0 224c0 8.8 7.2 16 16 16s16-7.2 16-16l0-224c0-8.8-7.2-16-16-16zm96 0c-8.8 0-16 7.2-16 16l0 224c0 8.8 7.2 16 16 16s16-7.2 16-16l0-224c0-8.8-7.2-16-16-16zm96 0c-8.8 0-16 7.2-16 16l0 224c0 8.8 7.2 16 16 16s16-7.2 16-16l0-224c0-8.8-7.2-16-16-16z"
              />
            </svg>
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { reactive, computed, watch } from "vue";

export default {
  setup() {
    let data = reactive({
      newTodoName: "",
      todos: [],
    });

    const swearwords = ["fart", "poo", "willy"];

    let todosCount = computed(() => {
      return data.todos.length;
    });

    function addTodo() {
      let newTodo = {
        id: Date.now(),
        name: data.newTodoName,
      };
      data.todos.push(newTodo);
      data.newTodoName = "";
    }

    function deleteTodo(index) {
      data.todos.splice(index, 1);
    }

    watch(data, (newValue) => {
      if (swearwords.includes(newValue.newTodoName.toLowerCase())) {
        alert("You should not say " + newValue.newTodoName + "!!!");
        data.newTodoName = "";
      }
    });

    return {
      data,
      todosCount,
      addTodo,
      deleteTodo,
    };
  },
};
</script>
