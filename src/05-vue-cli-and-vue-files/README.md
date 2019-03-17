Vue CLI and .vue files
------------
In our previous lesson we use cdn or add the vuejs file as a script tag, then we run our dev server.
<br >
But if you want to work with larger app or working with few developers that might not a good way.

* Install Vue CLI
  ```
  npm i -g @vue/cli @vue/cli-service-global
  ```
* Create new project with vue cli
  ```
  vue create hello-world
  ```
* Choose the `default (babel, eslint)`
  - this will initialize the project and install the dependencies
* Run the Application
  ```
  cd hello-world
  npm run serve
  ```
* Browse http://localhost:8080

<br />
.vue files
------------
* Folder structure
  - `public` contains all your public files that you will need
  - `src` all your vue files, assets and javascript files.
  - `src/components` contains all your reusable components
* Let's modify or update our `HelloWorld.vue` file
  ```html
  <template>
    <div>
      <h1>{{ message }}</h1>
    </div>
  </template>

  <script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        message: 'Hello World'
      }
    }
  }
  </script>
  ```
* Add styles to our `HelloWorld` component
  ```html
  <style scoped>
    h1 {
      color: red;
    }
  </style>
  ```