<template>
  <div>
    <home-navbar />
    <Nuxt />
    <contact-us-footer />
    <footer-component />
    <join-modal />
    <help-modal />
  </div>
</template>

<script>
import ContactUsFooter from '~/components/footers/ContactUsFooter.vue';
import FooterComponent from "~/components/footers/FooterComponent.vue";
import HelpModal from '~/components/modals/HelpModal.vue';
import JoinModal from "~/components/modals/JoinModal.vue";
import HomeNavbar from "~/components/navbars/HomeNavbar.vue";

export default {
  components: {
    HomeNavbar,
    FooterComponent,
    JoinModal,
    HelpModal,
    ContactUsFooter,
  },
};
</script>

<style>
</style>
