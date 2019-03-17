Using 3rd Party Libraries
------------

* Install `vue-material`
  ```
  npm install vue-material
  ```
* Add the following to your `main.js`
  ```javascript
  import VueMaterial from 'vue-material'
  import 'vue-material/dist/vue-material.min.css'
  import 'vue-material/dist/theme/default.css'

  Vue.use(VueMaterial)
  ```
* Now you can use material component
* Change your table list to material table (Please see `material.html`)
  - We can use `v-for` to loop thru list
* Using `v-model` to bind the list to the marterial table (Please see `material-v-model.html`)
* Let's add toolbar in `material table`
  ```html
  <md-table-toolbar>
    <div class="md-toolbar-section-start">
      <h1 class="md-title">Users</h1>
    </div>

    <md-field md-clearable class="md-toolbar-section-end">
      <md-input placeholder="Search by name..." v-model="search" @input="onSearch"  />
    </md-field>
  </md-table-toolbar>
  ```
* Adding `search` as `v-model` that holds the search key
  ```javascript
  data() {
    return {
      search: null
      ...
    }
  }
  ```
* Also let's add `onSearch` method to trigger everytime `search` key changed
  ```javascript
  methods: {
    onSearch() {
      const toLower = text => text.toString().toLowerCase()
      const searchByName = (items, term) => {
        if (term) {
          return items.filter(item => toLower(item.name).includes(toLower(term)))
        }
        return items
      }
      fetch('/user-list.json')
        .then(res => res.json())
        .then(data => searchByName(data, this.search))
        .then(result => {
          this.profiles = result;
        })
    }
  }
  ```
