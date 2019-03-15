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