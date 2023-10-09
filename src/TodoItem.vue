<template>
  <div class="todo-item" v-bind:class="{ completed: todoItem.completed }">
    <p @click="markComplete">
      {{ todoItem.title }}
    </p>
    <button @click="$emit('delete-todo-event', todoItem.id)">Delete</button>
  </div>
</template>

<script>
export default {
  name: 'ToDoItem',
  components: {},
  props: ['todoItem'],
  methods: {
    markComplete() {
      // eslint-disable-next-line vue/no-mutating-props
      this.todoItem.completed = !this.todoItem.completed;
    },
  },
};
</script>

<style>
.todo-item {
  max-width: 300px;
  display: flex;
  justify-content: space-around;
}

.completed {
  text-decoration: line-through;
}
</style>
