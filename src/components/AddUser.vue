<template>
  <div class="AddUser">
    <h2>Add new user:</h2>
    <form>
      <input type="text" name="firstName" v-model="firstName">
      <input type="text" name="lastName" v-model="lastName">
      <input type="email" name="email" :value="email" @input="email = $event.target.value">
      <button @click="addUser()" type="button">Add user</button>
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
      // const newUser = { firstName: this.firstName, lastName: this.lastName, email: this.email };

      this.$emit('add-user', this.$data);
    },
  },
};
</script>
