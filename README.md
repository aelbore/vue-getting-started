# Vue Getting Started
Step by Step to learn Vuejs


Requirements
------------
* Nodejs 8 or latest
* Text Editor (VSCode recommended)
* Development Server
  ```
  npm install -g http-server
  ```
* Download Materials
  ```
  https://github.com/aelbore/vue-getting-started.git
  ```

<br />

What is Vue or VueJS?
------------
Vue (pronounced /vjuː/, like view), is a javascript library to create reactive component for modern web.

* Features
  * Make your app reactive
  * Replace for jquery or a modern jquery, comparible to React and Angular
  * Great for controlling DOM, like for instance if you want to dynamically render list of data
  * Can create Single Page Application

  <br />
VueJS "Hello World"
------------
There are different options of installing vuejs (npm, cdn, or cli). 
You can use also webpack or vue-cli as part of your workflow.

* Download or use the cdn
* Add VueJS library as script tag
  ```html
    <script src="https://unpkg.com/vue/dist/vue.js"></script>
  ```
* Add markup to the body
  ```html
  <div id="app">
    <h1>{{ message }}</h1>
  </div>
  ```
* Create `hello-world.js` file
  ```javascript
  new Vue({
    el: '#app',
    data() {
      return {
        message: 'Hello World'
      }
    }
  }) 
  ```
* Add `hello-world.js` as script tag
  ```html
  <script src="hello-world.js"></script>
  ```


  <br />
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

  <br />
Data Bindings
------------

* Copy the `hello-world.js` file from `getting-started` folder to `data-bindings` folder
* Add markup 
  ```html
  <div id="app">
    <input type="text" v-on:input="name = $event.target.value" />
    <h1>Hello {{ name }}</h1>
  </div>
  ```
* Another example
  ```html
  <div id="app"> 
    <input type="text" v-on:input="name = $event.target.value" />
    <h1>Hello {{ name }}</h1>

    <input type="text" @input="age = $event.targer.textColor" />
    <h1 :class="textColor">{{ name }}</h1>
  </div>
  ```
* Update our `hello-world.js`
  ```javascript
  new Vue({
    el: '#app',
    data() {
      return {
        name: '',
        textColor: 'green'
      }
    }
  }) 
  ```
* add `style`
  ```html
  <style>
    .green {
      color: green;
    }
    .red {
      color: red;
    }
  </style>
  ```
