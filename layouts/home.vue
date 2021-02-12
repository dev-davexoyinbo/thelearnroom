<template>
  <div>
    <home-navbar />
    <Nuxt />
    <footer-component />
  </div>
</template>

<script>
import FooterComponent from "~/components/footers/FooterComponent.vue";
import HomeNavbar from "~/components/navbars/HomeNavbar.vue";

export default {
  components: {
    HomeNavbar,
	FooterComponent
  },
};
</script>

<style>
</style>
