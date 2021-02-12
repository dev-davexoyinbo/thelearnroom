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

	a {
		color: white;
	}
}
</style>