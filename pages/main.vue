<template>
  <div>
    <h1>main</h1>
    <div>
      <ul>
        <li v-for="product of products" :key="product.id">
          {{ product }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  //async created 의 문제점 : 데이터 불러오는 동안 빈 상태로 화면을 놔둠
  async created() {
    const res = await axios.get('http://localhost:3000/products');
    console.log(res);
    this.products = res.data;
  },
  data() {
    return {
      products: [],
    };
  },
};
</script>

<style></style>
