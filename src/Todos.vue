<template>
  <div>
    <h1>Todo List</h1>
  </div>

  <ul>
    <li v-bind:key="item.id" v-for="item in todoEntries">
      <TodoItem
        v-bind:todoItem="item"
        @delete-todo-event="$emit('delete-todo-event', item.id)"
      />
    </li>
  </ul>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  name: 'TodoList',
  components: {
    TodoItem,
  },
  props: ['todoEntries'],
};
</script>
