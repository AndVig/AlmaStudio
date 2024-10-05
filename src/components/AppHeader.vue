<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid d-flex justify-content-around">
      <!-- Button 1 and 2 will be hidden on small screens -->
      <div class="d-none d-lg-block">
        <button class="btn btn-primary">{{ button1Text }}</button>
        <button class="btn btn-primary">{{ button2Text }}</button>
      </div>
      <!-- Logo -->
      <a class="navbar-brand" href="#">
        <img src="/logo.jpg" class="rounded-circle" height="100rem" />
      </a>
      <!-- Button 3 and 4 will be hidden on small screens -->
      <div class="d-none d-lg-block">
        <button class="btn btn-primary">{{ button3Text }}</button>
        <button class="btn btn-primary">{{ button4Text }}</button>
      </div>
      <!-- Toggle button for small screens -->
      <button class="navbar-toggler" type="button" @click="isMenuOpen = !isMenuOpen">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
          stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 9h16.5m-16.5 6.75h16.5" />
        </svg>
      </button>
      <!-- Collapsible menu for small screens -->
      <div class="vis">

        <div :class="['collapse', 'navbar-collapse',{ 'show': isMenuOpen }]">
          <ul class="navbar-nav vis my-2">
            <li>
              <button class="btn btn-primary my-2">{{ button1Text }}</button>
            </li>
            <li>
              <button class="btn btn-primary my-2">{{ button2Text }}</button>
            </li>
            <li>
              <button class="btn btn-primary my-2">{{ button3Text }}</button>
            </li>
            <li>
              <button class="btn btn-primary my-2">{{ button4Text }}</button>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'AppHeader',
  data() {
    return {
      isMenuOpen: false,
      button1Text: 'Button 1',
      button2Text: 'Button 2',
      button3Text: 'Button 3',
      button4Text: 'Button 4'
    }
  },
  mounted() {
    window.addEventListener('resize', this.handleResize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    handleResize() {
      if (window.innerWidth > 900) {
        this.isMenuOpen = false;
      }
    }
  }
}
</script>

<style scoped>
.navbar {
  padding: 1rem 2rem;
}

.navbar-brand {
  margin: 0 20px;
}

.btn {
  margin: 0 10px;
}
.vis{
  display:none;
}
.navbar-toggler:focus {
  outline: none;
  box-shadow: none;
  /* box-shadow: 0 0 0 0.1rem rgba(37, 49, 62, 0.25); */
}
@media (max-width: 960px) {
  .d-lg-block {
    display: none;
  }
  .navbar-brand {
      margin: 0 auto;
      display: block;
    }
  .navbar-toggler {
    display: block;
    border: none;
  }
  .vis{
  display:contents;
}

}
</style>