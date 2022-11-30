<template>
  <body>
    <HeaderPage />
    <MainPage />
  </body>
</template>

<script>
import HeaderPage from '@/components/HeaderPage.vue';
import MainPage from '@/components/MainPage.vue';

export default {
  name: 'App',
  comments: {
    HeaderPage,
    MainPage,
  },
};
</script>

<style lang="scss" scoped>

</style>
