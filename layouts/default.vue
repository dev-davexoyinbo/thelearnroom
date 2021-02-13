<template>
  <div id="this-nuxt-app">
    <global-navbar />
    <info-strip />
    <div id="this-nuxt-app-content">
      <Nuxt />
    </div>
    <footer-component />
    <help-modal />
  </div>
</template>
<script>
import FooterComponent from "~/components/footers/FooterComponent.vue";
import InfoStrip from '~/components/InfoStrip.vue';
import HelpModal from '~/components/modals/HelpModal.vue';
import GlobalNavbar from "~/components/navbars/GlobalNavbar";

export default {
  components: {
    GlobalNavbar,
    FooterComponent,
    InfoStrip,
    HelpModal,
  },
};
</script>

<style scoped>
#this-nuxt-app {
  min-height: var(--viewport-height);
  display: flex;
  flex-direction: column;
}

#this-nuxt-app-content {
  flex: 1;
}
</style>