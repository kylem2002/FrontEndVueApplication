<template>
    <div v-for="product in products" :key="product.productNames">
        {{ product.productNames }}, {{ product.ecoRating }}
    </div>
</template>

<script>
export default {
    name: 'ProductBox',
    props: {
        products: Array
    }
}
</script>

<style scoped>
</style>
