<template>
  <aside id="teachers-dashboard-sidebar" :class="{collapsed: collpased}">
    <div class="expand-collapse-button" :class="{collapsed: collpased}" @click="collpased = !collpased">
      <i class="fas fa-angle-right"></i>
    </div>

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
  data() {
    return {
      collpased: false
    }
  }
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#teachers-dashboard-sidebar {
  --sidebar-width: 250px;
  --left-value: calc(var(--sidebar-width) * -1);

  width: var(--sidebar-width);
  padding: 16px;
  position: fixed;
  left:  var(--left-value);
  top: calc(var(--teacher-navbar-height) + var(--info-strip-height));
  bottom: 0;
  overflow-y: auto;
  background: white;
  border-right: 1px solid $borderGray;
  box-shadow: 2px 0px 8px rgba($darkBorderGray, 0.3);
  transition: left ease-out 0.3s;

  &.collapsed {
    --left-value: 0px;

  }

  @media only screen and (min-width: 768px) {
    padding-top: 0;
    padding-left: 0;
    display: block;
    --sidebar-width: 250px;
    background: transparent;
    position: unset;
    box-shadow: unset;
    border: none;
  }

  @media only screen and (min-width: 1024px) {
    --sidebar-width: 300px;
  }

  .expand-collapse-button {
    position: fixed;
    left: calc(var(--left-value) + var(--sidebar-width));
    // top: calc(var(--teacher-navbar-height) + var(--info-strip-height) + 10px);
    height: 40px;
    width: 40px;
    background: rgba(#8AB012, 0.6);
     clip-path: polygon(75% 0%, 100% 50%, 75% 100%, 0% 100%, 25% 50%, 0% 0%);
    transition: left ease-out 0.3s, clip-path ease-out 1s;
    

    &.collapsed {
      clip-path: polygon(100% 0%, 75% 50%, 100% 100%, 25% 100%, 0% 50%, 25% 0%);
      background: rgba(#B0492C, 0.6);
    }
    @media only screen and (min-width: 768px) {
      display: none;
    }
  }

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