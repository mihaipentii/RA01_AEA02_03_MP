<template>
    <div class="cart">
        <h2>Cart</h2>

        <p>There are {{ totalItems }} articles in the cart.</p>

        <ul>
            <CartItem
                v-for="item in cart"
                :key="item.name"
                :item="item"
            />
        </ul>
        <p class="total">Total: {{ total }}€</p>
        <button @click="deleteCart">Delete cart</button>
    </div>
</template>


<script setup>
import { inject, computed } from 'vue';
import CartItem from './CartItem.vue';

const cart = inject('cart');

const total = computed(() =>
    cart.reduce((sum,p) => sum + p.price, 0)
)

const totalItems = computed(() => cart.length)

const deleteCart = () => {
    cart.splice(0, cart.length);
}
</script>

<style scoped>
.cart {
  background: rgba(255, 255, 255, 0.08);
  border: 2px solid #dfe3e7;
  border-radius: 16px;
  padding: 30px 18px 18px;
  box-sizing: border-box;
}

h2 {
  margin: 0 0 20px;
  font-size: clamp(2rem, 2vw, 2.8rem);
  line-height: 1.2;
  font-weight: 800;
}

p {
  margin: 0 0 8px;
  font-size: 1.05rem;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.total {
  margin: 18px 0 0;
  font-size: 1.15rem;
  font-weight: 800;
  text-align: right;
}

button {
  display: none;
}
</style>