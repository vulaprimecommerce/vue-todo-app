<template>
  <div class="App">
    <Todos v-bind:todoEntries="todoEntries" />
    <AddToDoButton
      @add-todo-event="addTodoItem"
      @delete-todo-event="deleteToDoItem"
    />
  </div>
</template>

<script>
import AddToDoButton from './AddToDoButton.vue';
import Todos from './Todos.vue';

export default {
  name: 'App',
  components: { Todos, AddToDoButton },
  data() {
    return {
      todoEntries: [
        {
          id: 1,
          title: 'title 1',
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodoItem(newTodoItem) {
      console.log('xin chao', newTodoItem);
      this.todoEntries = [...this.todoEntries, newTodoItem];
    },
    deleteToDoItem(id) {
      this.todoEntries = this.todoEntries.filter((item) => item.id !== id);
    },
  },
};
</script>
