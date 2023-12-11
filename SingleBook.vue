<template>
    <div :class="book.ecoRating ? 'eco-friendly' : 'less-eco-friendly'">
      <h2>{{ book.productNames }}</h2>
      <p>Eco Rating: {{ book.ecoRating }}</p>
      <p>Cost: {{ book.cost }}</p>
      <p>Materials: {{ book.materials }}</p>
      <p>Creator Details: {{ book.CreatorDetails }}</p>
      <p>Product Type: {{ book.productTypes }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'SingleBook',
    props: {
      book: Object
    }
  }
  </script>
  
  <style scoped>
  .eco-friendly {
    background-color: #bdecb6;
  }
  
  .less-eco-friendly {
    background-color: #ffb89e;
  }
  
  div {
    color: black;
    padding: 1em;
    text-align: center;
    width: 80%;
    margin: auto;
    border: 1px solid #ddd;
    border-radius: 8px;
    margin-bottom: 10px;
  }
  
  h2 {
    margin: 5px 0;
  }
  
  p {
    margin: 2px;
  }
  </style>
  