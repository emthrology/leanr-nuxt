<template>
  <div>
    <!-- layouts에 error.vue 로 생성하면 자동 fallback 연결됨 -->
    <h1>Error Occured {{ error.statudCode }}</h1>
    <p>{{ error.message }}</p>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: () => {},
    },
  },
};
</script>

<style></style>
