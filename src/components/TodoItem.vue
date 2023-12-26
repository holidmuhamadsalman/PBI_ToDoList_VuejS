<template>
  <li>
    {{ todo }}
    <button @click="deleteThisTodo">Hapus</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: String,
      required: true,
    },
  },
  methods: {
    deleteThisTodo() {
      this.$emit('deleteTodo');
    },
  },
};
</script>

<style scoped>

li {
  margin: 5px 0;
  padding: 8px;
  background-color: #f4f4f4;
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
