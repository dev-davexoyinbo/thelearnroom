<template>
  <div>
    <hero-section />
    <online-classes-section />
    <customize-child-learning-section />
  </div>
</template>

<script>
import CustomizeChildLearningSection from '~/components/page_specific/home/CustomizeChildLearningSection.vue';
import HeroSection from "~/components/page_specific/home/HeroSection.vue";
import OnlineClassesSection from "~/components/page_specific/home/OnlineClassesSection.vue";
export default {
  components: { HeroSection, OnlineClassesSection, CustomizeChildLearningSection },
  layout: "home",
};
</script>

    