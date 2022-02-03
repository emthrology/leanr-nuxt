<template>
  <div>
    <h1>main</h1>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  async created() {
    const res = await axios.get('http://localhost:3000/products');
    console.log(res);
  },
};
</script>

<style></style>
