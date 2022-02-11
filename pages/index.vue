<template>
  <div class="app">
    <div>
      <input type="text" />
    </div>
    <main>
      <ProductList :products="products" @productClick="moveToDetailPage" />
    </main>
  </div>
</template>

<script>
import axios from 'axios';
import ProductList from '@/components/ProductList.vue';
export default {
  components: {
    ProductList,
  },
  //nuxt data feature - asyncData()
  //1.async 기본 사용
  //2.this - vm 바인딩 이전에 작동
  //3.리턴값이 곧바로 data()처럼 작동
  //4.pages폴더 안에서만 적용되는 프로퍼티이다.(주의!)
  async asyncData(context) {
    try {
      const res = await axios.get('http://localhost:3000/products');
      // eslint-disable-next-line prettier/prettier
      const products = res.data.map((product) => ({
        ...product,
        imageUrl: `${product.imageUrl}?random=${Math.random()}`,
      }));
      return { products };
    } catch (error) {
      console.log(error);
      context.error({
        statudCode: error.response.status,
        message: error.message,
      });
    }
  },
  methods: {
    //param destructuring - product.id
    moveToDetailPage({ id }) {
      console.log({ id });
    },
  },
  //async created 의 문제점 : 데이터 불러오는 동안 빈 상태로 화면을 놔둠
  // async created() {
  //   const res = await axios.get('http://localhost:3000/products');
  //   console.log(res);
  //   this.products = res.data;
  // },
  // data() {
  //   return {
  //     products: [],
  //   };
  // },
};
</script>

<style scoped>
.app {
  position: relative;
}
</style>
