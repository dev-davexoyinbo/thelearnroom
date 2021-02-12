<template>
  <div>
    <home-navbar />
    <Nuxt />
    <footer-component />
    <join-modal />
  </div>
</template>

<script>
import FooterComponent from "~/components/footers/FooterComponent.vue";
import JoinModal from "~/components/modals/JoinModal.vue";
import HomeNavbar from "~/components/navbars/HomeNavbar.vue";

export default {
  components: {
    HomeNavbar,
    FooterComponent,
    JoinModal,
  },
};
</script>

<style>
</style>
