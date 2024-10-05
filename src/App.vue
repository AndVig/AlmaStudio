<script>
import AppHeader from './components/AppHeader.vue';
import AppHome from './pages/AppHome.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    // AppFooter,
    AppHome,
  }
}
</script>

<template>
  <AppHeader />
  <AppHome />
</template>

<style>

</style>
