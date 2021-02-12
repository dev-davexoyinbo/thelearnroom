<template>
  <div>
    <hero-section />
    <online-classes-section />
  </div>
</template>

<script>
import HeroSection from "~/components/page_specific/home/HeroSection.vue";
import OnlineClassesSection from "~/components/page_specific/home/OnlineClassesSection.vue";
export default {
  components: { HeroSection, OnlineClassesSection },
  layout: "home",
};
</script>

    