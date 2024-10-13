<template>
  <div>
    <input type="text" v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new task" />
    <button @click="addTodo">Add</button>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
  data() {
    return {
      newTodo: ''
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() === '') return;
      const newTodo = {
        id: Date.now(),
        text: this.newTodo,
        completed: false
      };
      this.$emit('add-todo', newTodo);
      this.newTodo = '';
    }
  }
};
</script>

<style scoped>
input {
  margin-right: 10px;
}
</style>
