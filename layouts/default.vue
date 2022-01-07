<template>
  <div>
    <AppHeader />
    <!-- SPA vue project에서의 router-view -->
    <Nuxt />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";

export default {
  components: { AppHeader },
};
</script>
//
