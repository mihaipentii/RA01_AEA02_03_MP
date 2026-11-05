<template>
  <div class="container">
    <h1>Botiga de gadgets</h1>
    <div class="content">
      <CategoryList />
      <Cart />
    </div>
  </div>
</template>

<script setup>
import { reactive ,provide } from 'vue';
import CategoryList from './components/CategoryList.vue';
import Cart from './components/Cart.vue';

const cart = reactive([])
const products = [
  { name: "Auriculars Wireless 🎧", price: 50 },
  { name: "Smartwatch ⌚", price: 120 },
  { name: "Teclat Mecànic ⌨️", price: 80 },
  { name: "Altaveu Bluetooth 🔊", price: 60 }
]

provide('cart', cart)
provide('products', products)

</script>

<style>
body {
  margin: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: #f1f1f1;
  color: #1d1d1d;
}

#app {
  min-height: 100vh;
}

.container {
  max-width: 1220px;
  margin: 28px auto 0;
  background: rgba(255, 255, 255, 0.12);
  border: 2px solid #dfe0e2;
  border-radius: 18px;
  padding: 34px 28px 26px;
  box-sizing: border-box;
}

h1 {
  margin: 0 0 30px;
  text-align: center;
  font-size: clamp(2.6rem, 4vw, 4rem);
  line-height: 1.1;
  font-weight: 800;
  letter-spacing: -0.05em;
}

.content {
  display: grid;
  grid-template-columns: minmax(0, 2.15fr) minmax(270px, 0.9fr);
  gap: 34px;
  align-items: start;
}
</style>