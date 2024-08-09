<template>
  <b-navbar toggleable="lg" type="dark" variant="dark" class="w-100">
    <b-navbar-brand href="#">Assistente de bate-papo em PDF</b-navbar-brand>
  </b-navbar>
</template>

<script>
import {BNavbar, BNavbarBrand} from "bootstrap-vue-next";

export default {
  name: 'NavbarComponent',
  components: {BNavbar, BNavbarBrand}
}
</script>

<style scoped>
.navbar {
  background-color: #343a40;
  padding: 1rem;
}
.navbar-brand {
  color: #fff;
  text-decoration: none;
}
</style>

