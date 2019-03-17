<template>
  <div>
    <md-table md-card>

      <md-table-row>
        <md-table-head hidden md-numeric>ID</md-table-head>
        <md-table-head>Name</md-table-head>
        <md-table-head>Title</md-table-head>
        <md-table-head>Email</md-table-head>
      </md-table-row>

      <md-table-row  v-for="(profile, index) in profiles" v-bind:key="index">
        <md-table-cell hidden md-numeric>{{ profile.id }}</md-table-cell>
        <md-table-cell>{{ profile.name }}</md-table-cell>
        <md-table-cell>{{ profile.title }}</md-table-cell>
        <md-table-cell>{{ profile.email }}</md-table-cell>
      </md-table-row>

    </md-table>
  </div>
</template>

<script>
export default {
  name: 'UserList',
  created() {
    fetch('/user-list.json')
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
