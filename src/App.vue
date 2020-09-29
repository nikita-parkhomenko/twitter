<template>
  <div id="app">
    @{{ user.userName }} - {{ fullName }}
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      followers: 100,
      user: {
        userName: 'nekit_park',
        firstName: 'Nikita',
        lastName: 'Parkhomenko',
        email: 'nikita.parkhom@gmail.com',
        id: 1,
        isAdmin: true,
      }
    }
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
