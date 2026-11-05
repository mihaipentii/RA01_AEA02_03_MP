<template>
    <div class="product-item">
        <div class="product-info">
            <span class="name">{{ product.name }}</span>
            <span class="price">{{ product.price }}€</span>     
        </div>
        <button @click="addToCart">Add to cart</button>
    </div>
</template>

<script setup>
import { inject } from 'vue';

const props = defineProps(['product']);
const cart = inject('cart');

const addToCart = () => {
    cart.push(props.product);
    alert(`${props.product.name} added to the cart!`);
}

</script>

<style scoped>
.product-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 14px;
  min-height: 80px;
  border: 1px solid #dfe3e7;
  border-radius: 12px;
  background: rgba(255, 255, 255, 0.18);
  padding: 0 18px 0 20px;
  box-sizing: border-box;
}

.product-info {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex: 1;
  min-width: 0;
  gap: 16px;
}

.name {
  font-size: 1.05rem;
  font-weight: 500;
  color: #1d1d1d;
}

.price {
  margin-left: auto;
  font-size: 1.05rem;
  font-weight: 500;
  color: #1d1d1d;
}

button {
  background: #1eab8b;
  border: none;
  border-radius: 10px;
  color: white;
  font-size: 1.15rem;
  font-weight: 600;
  padding: 0.7rem 1.4rem;
  cursor: pointer;
  min-width: 140px;
  transition: filter 0.2s ease;
}

button:hover {
  filter: brightness(0.98);
}
</style>