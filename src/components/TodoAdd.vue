<template>
  <div>
    <input v-model="newTodo" type="text" placeholder="Tambah To-Do" />
    <button @click="addNewTodo">Tambah</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
    };
  },
  methods: {
    addNewTodo() {
      if (this.newTodo.trim() !== '') {
        this.$emit('addTodo', this.newTodo);
        this.newTodo = '';
      }
    },
  },
};
</script>

<style scoped>

input {
  padding: 8px;
  margin-right: 8px;
  border: 1px solid #ccc;
  border-radius: 3px;
}

button {
  padding: 8px 16px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}
</style>

