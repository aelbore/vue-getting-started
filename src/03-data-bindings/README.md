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