<template>
  <div class="home-teacher-card">
    <div class="top"></div>
    <div class="bottom">
      <div class="name">John D</div>
      <div class="position">Web Designer</div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "~assets/styles/variables";

.home-teacher-card {
	background: rgba($neutralHighlight, 0.5);
  .top {
    height: 150px;
    background: $placeholderGray;
	border-radius: 5px;
  }
  .bottom {
	  padding: 16px;
	  text-align: center;
	  .name {
		  color: black;
	  }
  }
}
</style>