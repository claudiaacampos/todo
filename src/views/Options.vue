<template>
  <div class="home">
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
      <ul>
        <li v-for="(todo, index) in todos" :key="todo.id">
          <span>{{ todo.name }}</span>
          <button @click="deleteTodo(index)">X</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoName: '',
      todos: [
        {
          id: 1,
          name: 'One'
        },
        {
          id: 2,
          name: 'Two'
        },
        {
          id: 3,
          name: 'Three'
        },
        {
          id: 4,
          name: 'Four'
        },
        {
          id: 5,
          name: 'Five'
        },
      ],
      swearwords: ['fart', 'butt hair', 'willy']
    }
  }, 
  computed: {
    todosCount() {
      return this.todos.length;
    }
  },
  methods: {
    addTodo() {
      let newTodo = {
        id: Date.now(),
        name: this.newTodoName,
      };
      this.todos.push(newTodo);
      this.newTodoName = '';
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
  watch: {
    newTodoName(newValue) {
      console.log('newValue: ', newValue);
      if (this.swearwords.includes(newValue.toLowerCase())) {
        this.newTodoName = '';
        alert('You should not say ' + newValue + '!!!')
      };
    }
  }
}
</script>

