<template>
  <div id="app">
    <h1>To-Do List</h1>
    <AddTodo @add-todo="addTodo" />
    <TodoList :todos="todos" @delete-todo="deleteTodo" @toggle-complete="toggleComplete" />
  </div>
</template>

<script>
import AddTodo from './components/AddTodo.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
  components: {
    AddTodo,
    TodoList
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo);
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    toggleComplete(id) {
      const todo = this.todos.find(todo => todo.id === id);
      if (todo) {
        todo.completed = !todo.completed;
      }
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
