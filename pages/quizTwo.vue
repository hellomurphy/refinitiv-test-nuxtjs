<script>
export default {
  data() {
    return {
      fetchedData: [],
      search: '',
    }
  },
  async fetch() {
    await fetch('https://api.publicapis.org/categories')
      .then((res) => res.json())
      .then((data) => (this.fetchedData = data.categories))
  },
  computed: {
    filteredData() {
      return this.fetchedData.filter((data) =>
        data.toLowerCase().includes(this.search.toLowerCase())
      )
    },
  },
}
</script>

<template>
  <div class="">
    <h1 class="text-lg">Quiz2</h1>
    <div>
      <input type="text" class="border shadow rounded" v-model="search" />
    </div>
    <div>
      <ul class="list-decimal">
        <li v-for="data in filteredData" :key="data">
          {{ data }}
        </li>
      </ul>
    </div>
  </div>
</template>