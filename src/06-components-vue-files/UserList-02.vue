<template>
  <table>
    <tr>
      <th>Name</th>
      <th>Email</th>
    </tr>
    <tr v-for="(profile, index) in profiles" v-bind:key="index">
      <td>{{ profile.name }}</td>
      <td>{{ profile.email }}</td>
    </tr>
  </table>  
</template>

<script>
export default {
  name: 'UserList',
  created() {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(res => res.json())
      .then(data => {
        this.profiles = data;
      })
  },
  data() {
    return {
      profiles: []   
    }
  }
}
</script>

<style scoped>
table {
  border-collapse: collapse;
  border-spacing: 0;
  width: 100%;
  border: 1px solid #ddd;
}

th, td {
  text-align: left;
  padding: 16px;
}

tr:nth-child(even) {
  background-color: #f2f2f2
}
</style>