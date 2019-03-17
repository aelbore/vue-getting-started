<template>
  <div id="app">
    <h1>My Page</h1>
    <UserList />
  </div>
</template>

<script>
import UserList from './components/UserList.vue'

export default {
  name: 'app',
  components: {
    UserList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 10px;
  padding: 50px;
}
</style>
