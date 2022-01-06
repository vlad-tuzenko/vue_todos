<template>
  <div class="App">
    <nav>
      <button @click="modalUser = !modalUser">Add user</button>
      <button @click="modalTodo = !modalTodo">Add todo</button>
    </nav>
    <AddUser v-if="modalUser" v-on:add-user="addNewUser"/>
    <AddTodo v-if="modalTodo" :userList="users" v-on:add-todo="addNewTodo"/>
    <TodosList :todos="todos" v-on:delete-todo="deleteTodo"/>
  </div>
</template>

<script>
import TodosList from './components/TodosList.vue';
import AddUser from './components/AddUser.vue';
import AddTodo from './components/AddTodo.vue';

export default {
  name: 'App',
  data() {
    return {
      todos: [
        { text: 'Make todos list using Vue', email: 'johnsmith@gmail.com' },
        { text: 'Add button for remove item', email: 'johnsmith@gmail.com' },
      ],
      users: [{ firstName: 'John', lastName: 'Smith', email: 'johnsmith@gmail.com' }],
      modalUser: false,
      modalTodo: false,
    };
  },
  components: {
    TodosList,
    AddUser,
    AddTodo,
  },
  methods: {
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
    addNewUser(user) {
      this.users.push(user);
      this.modalUser = !this.modalUser;
    },
    addNewTodo(todo) {
      this.todos.push(todo);
      this.modalTodo = !this.modalTodo;
    },
  },
};
</script>

<style>

</style>
