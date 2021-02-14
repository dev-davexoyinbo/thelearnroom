<template>
  <div ref="teacherNavbar" class="teacher-navbar">
    <div class="top">
      <div class="heading">Teaching</div>
    </div>
    <div class="bottom">
      <div class="tabs-container">
        <div class="tabs">
          <a href="#" class="tab" :class="{active: $nuxt.$route.path==`/teachers/dashboard`}" >Dashboard</a>
          <a href="#" class="tab" :class="{active: $nuxt.$route.path==`/teachers/apply`}" >Apply</a>
          <a href="#" class="tab" :class="{active: $nuxt.$route.path==`/teachers/schedule`}" >Schedule</a>
          <a href="#" class="tab" :class="{active: $nuxt.$route.path==`/teachers/section`}" >Section</a>
          <a href="#" class="tab" :class="{active: $nuxt.$route.path==`/teachers/classes`}" >Classes</a>
          <a href="#" class="tab" :class="{active: $nuxt.$route.path==`/teachers/profile`}" >Profile</a>
          <a href="#" class="tab" :class="{active: $nuxt.$route.path==`/teachers/availability`}" >Availability</a>
          <a href="#" class="tab" :class="{active: $nuxt.$route.path==`/teachers/stats`}" >Stats</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted(){
    this.heightChangeHooks();
  },
  updated() {
    this.heightChangeHooks();
  },
  beforeDestroy() {
    document.documentElement.style.setProperty("--teacher-navbar-height", "0px");
  },
  methods: {
    heightChangeHooks() {
      const teacherNavbar = this.$refs.teacherNavbar;
      const height = getComputedStyle(teacherNavbar).height;

      document.documentElement.style.setProperty("--teacher-navbar-height", height);
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";

.teacher-navbar {
  color: white;
  background: $darkColorAlt;
  position: sticky;
  top: var(--info-strip-height);
  z-index: 9;
  .top {
    height: var(--teacher-navbar-top-height);
    display: flex;
    align-items: center;
    padding: 0 var(--body-padding);
    .heading {
      font-size: 1.7rem;
      font-weight: 400;
    }
  }

  .tabs-container {
    padding: 0 var(--body-padding);
  }

  .tabs {
	  display: flex;
    margin: 0;
    flex-wrap: nowrap;
    overflow-x: auto;
    scrollbar-width: none;
    scroll-behavior: smooth;
    /* Firefox */
    -ms-overflow-style: none;
    /* IE 10+ */
    &::-webkit-scrollbar {
      width: 0px;
      height: 0px;
      background: transparent;
      /* Chrome/Safari/Webkit */
    }
    .tab {
      height: 35px;
      font-size: 0.9rem;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0 12px;
      text-decoration: none;
      color: white;

      &:hover {
        background: lighten($darkColorAlt, 10%);
      }

      &.active {
        background: white;
        color: $darkColorAlt;
        &:hover {
          background: lighten($darkColorAlt, 70%);
        }
      }
    }
  }
}
</style>