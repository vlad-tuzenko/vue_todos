<template>
  <div class="TodoList">
    <h2 class="TodoList__title">Todos list:</h2>
    <ul class="TodoList__list">
      <li
        class="TodoList__item"
        v-for="(todo, index) in todos"
        :key="index"
      >
        <p class="TodoList__text">{{todo.text}}</p>
        <p class="TodoList__email">{{todo.email}}</p>
        <button class="TodoList__button" @click="deleteTodo(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodosList',
  props: ['todos'],
  methods: {
    deleteTodo(index) {
      this.$emit('delete-todo', index);
    },
  },
};
</script>

<style>
.TodoList {
  color: #000;
}

.TodoList__list {
  display: flex;
  padding: 0;
  flex-direction: column;
  gap: 10px;
  list-style: none;
}

.TodoList__item {
  width: 400px;
  padding: 20px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  border: 1px solid;
}

.TodoList__button {
  width: 70px;
}
</style>
