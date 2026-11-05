<template>
    <div class="category-list">
        <h2>Products</h2>
        <div class="products">
            <ProductItem v-for="p in products" :key="p.name" :product="p" />
        </div>
    </div>
</template>


<script setup>
import ProductItem from './ProductItem.vue';
import { inject } from 'vue';

const products = inject('products');
</script>

<style scoped src="../assets/styles/category-list.css"></style>