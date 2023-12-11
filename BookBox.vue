<template>
   
    

  <div v-for="book in books" :key="book.productNames">
    <SingleBook :book="book" />
  </div>


</template>
<script>
import SingleBook from './SingleBook.vue'

export default {
    name: 'BookBox',
    props:{
        books: Array
    },
    components:{
        SingleBook
    }
    
}
</script>
<style scoped>

</style>
