<template>
  <div>
    <ul>
      <li v-for="product of products" :key="product.id" class="item flex">
        <img
          :src="product.imageUrl"
          :alt="product.name"
          class="product-image"
          @click="emitEvent(product)"
        />
        <p>{{ product.name }}</p>
        <span>{{ product.price }}</span>
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
  methods: {
    emitEvent(product) {
      this.$emit('productClick', product);
    },
  },
};
</script>

<style scoped>
.flex {
  display: flex;
  justify-content: center;
}
.item {
  display: inline-block;
  width: 400px;
  height: 300px;
  text-align: center;
  margin: 0 0.5rem;
  cursor: pointer;
}
.product-image {
  width: 400px;
  height: 250px;
}

.cart-wrapper {
  position: sticky;
  float: right;
  bottom: 50px;
  right: 50px;
}
.cart-wrapper .btn {
  display: inline-block;
  height: 40px;
  font-size: 1rem;
  font-weight: 500;
}
</style>
