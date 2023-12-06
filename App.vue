<template>
  <MainHeader/>
  <ProductBox :products="products" />
  <CreditCaption/>

</template>

<script>
import MainHeader from './components/MainHeader.vue';
import ProductBox from './components/ProductBox.vue' 
import CreditCaption from './components/CreditCaption.vue';

export default {
  name: 'App',
  components: {
    MainHeader,
    ProductBox,
    CreditCaption
},
  data() {
    return {
      products: [], 
    }
  },
  methods: {
  async fetchProducts() {
    const res = await fetch("https://kylewebsite.onrender.com/api")
    const data = await res.json()
    console.log(data)
    return Array.isArray(data) ? data : [] 
    }
  },
  async created() {
    this.products = await this.fetchProducts() 
  }
}
</script>

<style>


.content {
  flex: 1;
}
</style>


