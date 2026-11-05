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

<style scoped src="../assets/styles/product-item.css"></style>