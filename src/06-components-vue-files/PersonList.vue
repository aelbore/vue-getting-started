<template>
  <ul>
    <li v-for="(person, index) in persons" v-bind:key="index">
      {{ person.name }}
    </li>
  <ul>
</template>

<script>
export default {
  name: 'PersonList',
  data() {
    return {
      persons: [
        { name: 'John', age: 20 },
        { name: 'Jane', age: 23 },
        { name: 'Bob', age: 22 }  
      ]
    }
  }
}
</script>

