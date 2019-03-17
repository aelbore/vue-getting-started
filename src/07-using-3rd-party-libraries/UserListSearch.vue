<template>
  <div>
    <md-table v-model="profiles" md-sort="name" md-sort-order="asc" md-card md-fixed-header>
      <md-table-toolbar>
        <div class="md-toolbar-section-start">
          <h1 class="md-title">Users</h1>
        </div>

        <md-field md-clearable class="md-toolbar-section-end">
          <md-input placeholder="Search by name..." v-model="search" @input="onSearch"  />
        </md-field>
      </md-table-toolbar>

      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="Name" md-sort-by="name">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Email" md-sort-by="email">{{ item.email }}</md-table-cell>
        <md-table-cell md-label="Gender" md-sort-by="gender">{{ item.gender }}</md-table-cell>
        <md-table-cell md-label="Job Title" md-sort-by="title">{{ item.title }}</md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: 'UserListSearch',
  mounted() {
    fetch('/user-list.json')
      .then(res => res.json())
      .then(data => {
        this.profiles = data;
      })
  },
  data() {
    return {
      search: null,
      profiles: []
    }
  },
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
}
</script>

<style scoped>
  .md-field {
    max-width: 300px;
  }

  table {
    border-collapse: collapse;
    border-spacing: 0;
    width: 100%;
    border: 1px solid #ddd;
  }

  th, td {
    text-align: left;
    padding: 0px;
  }

  tr:nth-child(even) {
    background-color: #f2f2f2
  }
</style>