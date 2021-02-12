<template>
  <div class="info-strip">
	  <p>The LearnRoom offers <a href="#">video chat classes</a>  by inspiring teachers.</p>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import '~assets/styles/variables';
.info-strip {
	background: $primaryColor;
	display: flex;
	align-items: center;
	justify-content: center;
	padding: 6px var(--body-padding);
	color: white;
	font-size: 0.9rem;
	text-align: center;

	position: sticky;
	top: var(--global-navbar-height);
	z-index: 11;
	box-shadow: 0px 3px 10px rgba($darkColor, 0.18);

	a {
		color: white;
	}
}
</style>