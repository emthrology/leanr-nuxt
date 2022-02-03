<template>
  <div>
    <ul>
      <li v-for="product of products" :key="product.id">
        {{ product }}
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
