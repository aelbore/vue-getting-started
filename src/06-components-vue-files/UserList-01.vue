<template>
  <div>
    <ul>
      <li v-for="(person, index) in persons" v-bind:key="index">
        {{ person.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'UserList',
  created() {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(res => res.json())
      .then(data => {
        this.persons = data.map(user => ({ name: user.name }))
      })
  },
  data() {
    return {
      persons: []   
    }
  }
}
</script>