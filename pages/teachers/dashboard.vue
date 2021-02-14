<template>
  <div id="teachers-dashboard-page">
    <teacher-dashboard-sidebar />
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
import TeachersCoursesCard from '~/components/page_specific/teachers/dashboard/TeachersCoursesCard.vue';
export default {
  layout: "teachers",
  components: {
    TeacherDashboardSidebar,
    TeachersCoursesCard,
  },
};
</script>

<style lang="scss">
@import '~assets/styles/variables';

#teachers-dashboard-page {
  padding: 24px var(--body-padding);
  display: grid;
  grid-template-columns: max-content 1fr;
  gap: 24px;

  .profile-section {
	  display: grid;
	  grid-template-columns: 150px 1fr;
	  gap: 32px;
	  align-items: center;
	  margin-top: 24px;
	  margin-bottom: 24px;

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