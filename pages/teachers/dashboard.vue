<template>
  <div id="teachers-dashboard-page">
	  <teachers-dashboard-sidebar />
	  <div class="main-content">
		  <h2 class="h2">Welcome To The Learnroom!!</h2>
	  </div>
  </div>
</template>

<script>
import TeachersDashboardSidebar from '~/components/page_specific/teachers/dashboard/TeachersDashboardSidebar.vue'
export default {
  components: { TeachersDashboardSidebar },
	layout: 'teachers'
}
</script>

<style lang="scss">
#teachers-dashboard-page {
	padding: 24px var(--body-padding);
	display: grid;
	grid-template-columns: max-content 1fr;
	gap: 24px;
}
</style>