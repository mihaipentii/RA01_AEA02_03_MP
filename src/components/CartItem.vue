<template>
    <li>
        {{ item.name }} - {{ item.price }}€
    </li>
</template>

<script setup>
defineProps({
    item: {
        type: Object,
        required: true
    }
});
</script>

<style scoped src="../assets/styles/cart-item.css"></style>