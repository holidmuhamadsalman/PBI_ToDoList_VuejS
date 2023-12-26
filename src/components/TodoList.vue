<template>
  <div>
    <h2>Daftar Todo List</h2>
    <ul>
      <TodoItem
        v-for="(todo, index) in todos"
        :key="index"
        :todo="todo"
        @deleteTodo="deleteTodo(index)"
      />
    </ul>
    <TodoAdd @addTodo="addTodo" />
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';
import TodoAdd from './TodoAdd.vue';

export default {
  components: {
    TodoItem,
    TodoAdd,
  },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style scoped>

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin: 5px 0;
  padding: 8px;
  background-color: #1b1a1a;
  border-radius: 4px;
}

button {
  padding: 4px 8px;
  background-color: #ff4c4c;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>

