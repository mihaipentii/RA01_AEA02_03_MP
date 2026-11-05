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

<style scoped>
li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
  padding: 12px 0;
  border-bottom: 1px solid #e4e4e4;
  font-size: 1.05rem;
  font-weight: 500;
}
</style>