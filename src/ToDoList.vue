<template>
  <div>
    <TodoItem
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      @delete-todo="$emit('delete-todo', todo.id)"
      @toggle-complete="$emit('toggle-complete', todo.id)"
    />
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  name: 'TodoList',
  components: {
    TodoItem
  },
  props: {
    todos: Array
  }
};
</script>

<style scoped>
</style>
