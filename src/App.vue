<script setup>
import ProductsTable from "./components/ProductsTable.vue"
import Products from "./components/productList.json"
</script>

<template>
  <main>
    <ProductsTable :products="Products"/>
  </main>
</template>



