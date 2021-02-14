<template>
  <div id="this-nuxt-app">
    <info-strip :stickTop="true" :confirmEmail="true" :welcomeMessage="false"/>
	<teachers-navbar />
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
import TeachersNavbar from '~/components/navbars/TeachersNavbar.vue';

export default {
  components: {
    FooterComponent,
    InfoStrip,
    HelpModal,
    TeachersNavbar,
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