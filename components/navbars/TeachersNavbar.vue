<template>
  <div class="teacher-navbar">
    <div class="top">
      <div class="heading">Teaching</div>
    </div>
    <div class="bottom">
      <div class="tabs-container">
        <div class="tabs">
          <a href="#" class="tab">Dashboard</a>
          <a href="#" class="tab">Apply</a>
          <a href="#" class="tab">Schedule</a>
          <a href="#" class="tab">Section</a>
          <a href="#" class="tab active">Classes</a>
          <a href="#" class="tab">Profile</a>
          <a href="#" class="tab">Availability</a>
          <a href="#" class="tab">Stats</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "~assets/styles/variables";

.teacher-navbar {
  color: white;
  background: $darkColorAlt;
  position: sticky;
  top: var(--info-strip-height);
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