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

<style scoped src="../assets/styles/cart.css"></style>