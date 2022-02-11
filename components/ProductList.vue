<template>
  <div>
    <ul>
      <li v-for="product of products" :key="product.id">
        {{ product }}
        <img :src="product.imageUrl" :alt="product.name" />
        <p>{{ product.name }}</p>
        <p>{{ product.price }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    products: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style></style>
