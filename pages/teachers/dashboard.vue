<template>
  <div id="teachers-dashboard-page">
    <div class="teacher-dashboard-sidebar-container">
      
      <teacher-dashboard-sidebar />
    </div>
    <div class="main-content">
      <h2 class="h2">Welcome To The Learnroom!!</h2>
      <div class="profile-section">
        <div class="image-container">
          <img src="" alt="" />
        </div>
        <div>
          <p class="description">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit Nam eros
            tellus. Phasellus nec iaculis sapien
          </p>
        </div>
      </div>

      <div class="teachers-courses-cards-container">
        <teachers-courses-card v-for="i in 4" :key="i" />
      </div>
    </div>
  </div>
</template>

<script>
import TeacherDashboardSidebar from "~/components/page_specific/teachers/dashboard/TeacherDashboardSidebar.vue";
import TeachersCoursesCard from "~/components/page_specific/teachers/dashboard/TeachersCoursesCard.vue";
export default {
  layout: "teachers",
  components: {
    TeacherDashboardSidebar,
    TeachersCoursesCard,
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";

#teachers-dashboard-page {
  --page-top-padding: 24px;
  padding: var(--page-top-padding) var(--body-padding);

  @media only screen and (min-width: 768px) {
    display: grid;
    grid-template-columns: max-content 1fr;
    gap: 24px;
  }

  .teacher-dashboard-sidebar-container {
    position: relative;
    
  }

  .profile-section {
    margin-top: 24px;
    margin-bottom: 24px;
    display: grid;
    grid-template-columns: 150px 1fr;
    gap: 32px;
    align-items: center;

    .image-container {
      img {
        width: 100%;
        height: 150px;
        background: $placeholderGray;
      }
    }
    .description {
      max-width: 500px;
      font-size: 0.9rem;
    }
  }
}
</style>