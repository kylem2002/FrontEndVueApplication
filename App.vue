<template>
  <!-- Using components with props and data binding -->
  <MyHeader bookName="Environmentally Friendly Product Guide" yourName="Kyle Muldoon"/>
  <BookBox :books="books" />
</template>

<script>
// Importing components
import MyHeader from './components/MyHeader.vue'
import BookBox from './components/BookBox.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    BookBox
  },
  data() {
    return {
      books: [] // Placeholder for fetched data
    }
  },
  methods: {
    // Function to fetch books data
    async fetchBooks() {
      try {
        const response = await fetch('https://kylewebsite.onrender.com/api');
        if (!response.ok) {
          throw new Error(`HTTP error! Status: ${response.status}`);
        }
        const data = await response.json();
        // Assuming the JSON structure is { "books": [ ... ] }
        return data.books; // Extract just the array part
      } catch (error) {
        console.error("Fetch error: ", error);
      }
    }
  },
  async created() {
    // Fetching data when the component is created
    this.books = await this.fetchBooks();
  }
}
</script>

<style>
/* Your existing CSS styles */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div {
  margin-bottom: 0.5em;
}
</style>
