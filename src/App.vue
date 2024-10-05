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
  <div class="bg-light">
    <AppHeader />
    <AppHome />

  </div>
</template>

<style>

</style>
