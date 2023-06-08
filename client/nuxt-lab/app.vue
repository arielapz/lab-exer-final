<template>
  <div>
    <div v-for="item in data" :key="item.id">
      <!-- Display your data here -->
      <p>{{ item.field1 }}</p>
      <p>{{ item.field2 }}</p>
    </div>
    <button @click="previousPage">Previous</button>
    <button @click="nextPage">Next</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: [],
      currentPage: 1,
    };
  },
  methods: {
    fetchData() {
      // Make an API request to the Laravel API endpoint
      // Include the "currentPage" parameter for pagination
    },
    previousPage() {
      if (this.currentPage > 1) {
        this.currentPage--;
        this.fetchData();
      }
    },
    nextPage() {
      this.currentPage++;
      this.fetchData();
    },
  },
  mounted() {
    this.fetchData();
  },
};
</script>