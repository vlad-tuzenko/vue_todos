<template>
  <div>
    <h2>Add new todo:</h2>
    <form>
      <input type="text" v-model="text">
      <select v-model="email">
        <option value="" disabled selected>Choose user</option>
        <option
          v-for="(user, index) in userList"
          v-bind:value="user.email"
          v-bind:key="index"
        >
          {{user.email}}
        </option>
      </select>
      <button type="button" @click="addTodo">Add todo</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
  props: ['userList'],
  data() {
    return {
      text: '',
      email: '',
    };
  },
  methods: {
    addTodo() {
      this.$emit('add-todo', this.$data);
    },
  },
};
</script>
