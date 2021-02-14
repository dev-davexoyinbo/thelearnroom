<template>
  <aside id="teachers-dashboard-sidebar">
    <div class="last-update-box">
      <div class="small-box"></div>
      <span class="last-update-text">Last update 2021</span>
      <generic-button :primaryDark="true" :noBorder="true" :sizeFactor="0.9"
        >Edit Profile</generic-button
      >
    </div>

    <teachers-signup-card />

    <div class="tips-container">
      <h1 class="h1 heading">Tips</h1>
      <div class="tips">
        <div class="tip">
          <div class="h4 heading">Scheduling</div>
          <div class="description">
            Lorem ipsum dolor sit amet consectetur adipiscing elit ameat as elit
          </div>
          <div>
            <a href="#">Learn More</a>
          </div>
        </div>
        <div class="tip">
          <div class="h4 heading">Payment</div>
          <div class="description">
            Lorem ipsum dolor sit amet consectetur adipiscing elit ameat as elit
          </div>
          <div>
            <a href="#">Learn More</a>
          </div>
        </div>
        <div class="tip">
          <div class="h4 heading">Privacy</div>
          <div class="description">
            Lorem ipsum dolor sit amet consectetur adipiscing elit ameat as elit
          </div>
          <div>
            <a href="#">Learn More</a>
          </div>
        </div>
        <div class="tip">
          <div class="h4 heading">Features</div>
          <div class="description">
            Lorem ipsum dolor sit amet consectetur adipiscing elit ameat as elit
          </div>
          <div>
            <a href="#">Learn More</a>
          </div>
        </div>
      </div>
    </div>

	<div class="resources-container">
		<h1 class="h1 heading">Resources</h1>
		<div class="resources">
			<a href="#">Help Center</a>
			<a href="#">Training Center</a>
			<a href="#">Teaching Resource</a>
			<a href="#">Website Status</a>
			<a href="#">Product Update</a>
			<a href="#">Chat With Support</a>
		</div>
	</div>
  </aside>
</template>

<script>
import GenericButton from "~/components/buttons/GenericButton.vue";
import TeacherSignupCard from "~/components/page_specific/teachers/dashboard/TeacherSignupCard.vue";
export default {
  components: { GenericButton, TeacherSignupCard },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#teachers-dashboard-sidebar {
  width: 300px;
  padding: 16px;
  padding-top: 0;

  .last-update-box {
    padding: 24px 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
    border: 1px solid #e8e8e8;
    border-radius: 3px;
    margin-bottom: 24px;

    .small-box {
      height: 80px;
      width: 80px;
      border: 1px solid #e8e8e8;
      border-top-width: 4px;
      border-bottom-width: 2px;
    }
    .last-update-text {
      display: inline-block;
      margin-top: 8px;
      margin-bottom: 8px;
      font-size: 0.9rem;
    }
  }

  .tips-container {
    margin: 32px 0;
    & > .heading {
      margin-bottom: 24px;
    }

    .tip {
      margin-bottom: 24px;

      &:last-child {
        margin-bottom: 0;
      }
      & > .heading {
        margin-bottom: 4px;
      }

      .description {
        font-size: 0.9rem;
      }

      a {
        text-decoration: none;
        color: $primaryColor;
        font-size: 0.9rem;
        margin-top: 8px;
        display: inline-block;
      }
    }
  }

  .resources-container {
	  .heading {
		  margin-bottom: 20px;
	  }

	  .resources {
		  a {
			  text-decoration: none;
			  color: $primaryColor;
			  font-size: 0.9rem;
			  display: flex;
			  align-items: center;
			  height: 30px;
		  }
	  }
  }
}
</style>