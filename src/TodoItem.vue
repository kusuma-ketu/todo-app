<template>
  <div :class="{ completed: todo.completed }">
    <input type="checkbox" :checked="todo.completed" @change="toggleComplete" />
    <span>{{ todo.text }}</span>
    <button @click="deleteTodo">Delete</button>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    todo: Object
  },
  methods: {
    deleteTodo() {
      this.$emit('delete-todo');
    },
    toggleComplete() {
      this.$emit('toggle-complete');
    }
  }
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>
