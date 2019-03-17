Components and Vue files
------------

* Create `PersonList.vue` file to `components` folder
* Add this following code
  ```html
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
  ```
  * Add `PersonList` as component in `App.vue`

<br />
Component Lifecycle Hooks
------------
Lifecycle hooks are an important part of any serious component. You often need to know when your component is created, added to the DOM, updated, or destroyed.

* Lifecycle Hooks
  - `created` - are the very first hooks that run in your component. They allow you to perform actions before your component has even been added to the DOM. 
  - `mounted` - In the mounted hook, you will have full access to the reactive component, templates, and rendered DOM (via. this.$el)
* Use native `fetch` to call api data
  ```html
    <script>
    export default {
      name: 'PersonList',
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
  ```
* Now let's add styles and use table to list the users (Please check users.html file)