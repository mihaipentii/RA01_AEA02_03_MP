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

<style scoped>
.category-list {
  flex: 1;
}

h2 {
  margin: 0 0 20px;
  font-size: clamp(2rem, 2vw, 2.8rem);
  line-height: 1.2;
  font-weight: 800;
}

.products {
  display: flex;
  flex-direction: column;
  gap: 14px;
}
</style>