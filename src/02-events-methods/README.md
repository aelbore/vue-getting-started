Events and Methods
------------
Use events and methods to dynamically update the template or change and data properties

* Copy the `hello-name.js` file from `getting-started` folder to `events-methods` folder
* Add markup 
  ```html
  <div id="app">
    <h1>{{ message }}</h1>
  </div>
  ```
* Add button element and click event
  ```html 
  <button v-on:click="changeHeader"></button>
  ```
* Lets add methods `changedHeader` to our `hello-world.js`
  ```javascript
  new Vue({
    el: '#app',
    data() {
      return {
        message: 'Hello World'
      }
    },
    methods: {
      changedHeader() {
        this.message = "Hello Universe"
      }
    }
  }) 
  ```  
* We can also use `@click` as event
  ```html 
  <button @click="changeHeader"></button>
  ```