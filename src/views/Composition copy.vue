<template>
  <div class="flex">
    <img alt="Vue logo" src="../assets/logo.png">
    <h3>You have {{ todosCount }} Todos!</h3>
    <div>
      <input
       v-model="newTodoName"
       @keyup.enter="addTodo"
       placeholder="Add a Todo"
       type="text">
    </div>
    <div>
      <ul class="flex">
        <li v-for="(todo, index) in todos" :key="todo.id">
          <span>{{ todo.name }}</span>
          <button @click="deleteTodo(index)">X</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { ref, computed, watch } from 'vue';

export default {
  setup() {
    let newTodoName = ref('');
    let todos = ref([]);

    

    let todosCount = computed(() => {
      return todos.value.length;
    });

    const swearwords = ['fart', 'butt hair', 'willy'];

    function addTodo() {
      let newTodo = {
        id: Date.now(),
        name: newTodoName.value,
      };
      todos.value.push(newTodo);
      newTodoName.value = '';
    };

    function deleteTodo(index) {
      todos.value.splice(index, 1);
    };

    watch(newTodoName, (newValue) => {
        if (swearwords.includes(newValue.toLowerCase())) {
          newTodoName.value = '';
          alert('You should not say ' + newValue + '!!!')
        };
    });

    return {
      newTodoName,
      todos,
      addTodo,
      deleteTodo,
      todosCount
    }
  }
}
</script>

<style>
ul {
  list-style: none;
  padding: 0;
  width: 200px;
  margin: 20px auto 0;
}
li {
  border: 1px solid;
  display: flex;
  margin: 0 0 10px;
}
li span {
  flex-grow: 1;
}
</style>
