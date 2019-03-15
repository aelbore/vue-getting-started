Condition
------------
We take a look on how we can output conditionally a specific DOM or element.

* Let's paragraph to our div app.
  ```html
  <p>Im part-time visible</p>
  ```
* Now let's add condition to our `<p>` element. This will add or remove element to the DOM
  ```html
  <p v-if="show">Im part-time visible</p>
  ```
* Create a button element to control the hide/show of our `<p>` element
  ```html
  <button @click="showHide">Show / Hide</button>
  <p v-if="show">Im part-time visible</p>
  ```
* Create a method to be use in click event
  ```javascript
   methods: {
     showHide() {
       this.show = !this.show;
     }
   }
  ```
* Click the button, notice the `<p>` element will remove to the DOM
* Use the inspect in DevTools
* Check if the `<p>` was remove.
* Let's add `v-else` 
  ```html
  <button @click="showHide">Show / Hide</button>
  <p v-if="show">Im part-time visible</p>
  <p v-else>I am visible</p>
  ```

Collection, Array or List
------------
Display a data of array or list in the markup

* Let's display list of person. we can use `<ul>` and `<li` element
  ```html
  <ul>
    <li>{{ persons[0].name }}</li>
  <ul>
  ```
* This approach is not efficient, if we change or add, remove an item in array, we encounter issue/problem.
* Let's use `v-for` this will loop or iterate thru your array list.
  ```html
  <ul>
    <li v-for="person in persons">{{ person.name }}</li>
  <ul>
  ```
* You can access also the index of array
  ```html
  <ul>
    <li v-for="(person, index) in persons">{{ person.name }} - {{ index }}</li>
  <ul>
  ```
