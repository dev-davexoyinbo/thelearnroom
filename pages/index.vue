<template>
  <div>
    <hero-section />
    <online-classes-section />
    <customize-child-learning-section />
    <classes-by-subject-section />
    <testimonial-section />
    <meet-our-teacher-section />
  </div>
</template>

<script>
import ClassesBySubjectSection from "~/components/page_specific/home/ClassesBySubjectSection.vue";
import CustomizeChildLearningSection from "~/components/page_specific/home/CustomizeChildLearningSection.vue";
import HeroSection from "~/components/page_specific/home/HeroSection.vue";
import MeetOurTeacherSection from "~/components/page_specific/home/MeetOurTeacherSection.vue";
import OnlineClassesSection from "~/components/page_specific/home/OnlineClassesSection.vue";
import TestimonialSection from "~/components/page_specific/home/TestimonialSection.vue";
export default {
  components: {
    HeroSection,
    OnlineClassesSection,
    CustomizeChildLearningSection,
    ClassesBySubjectSection,
    TestimonialSection,
    MeetOurTeacherSection,
  },
  layout: "home",
};
</script>

    