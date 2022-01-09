<template>
  <div class="AddUser">
    <h2>Add new user:</h2>
    <form @submit="addUser">
      <input type="text" name="firstName" v-model="firstName" required>
      <input type="text" name="lastName" v-model="lastName" required>
      <input type="email" name="email" :value="email" @input="email = $event.target.value" required>
      <button type="submit">Add user</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddUser',
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
    };
  },
  methods: {
    addUser() {
      this.$emit('add-user', this.$data);
    },
  },
};
</script>
