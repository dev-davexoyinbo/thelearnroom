<template>
  <div class="browse-class-card">
	  <div class="top">
		  <span>Next Week</span>
	  </div>
	  <div class="bottom">
		  <div class="">Morning</div>
		  <div class="">Afternoon</div>
		  <div class="">Evening</div>
	  </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.browse-class-card {
	background: #0F3063;
	color: white;
	border-radius: 5px;
	overflow: hidden;
	.top {
		height: 70px;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 1.3rem;
		border-bottom: 1px solid white;
	}
	.bottom{
		display: flex;
		font-weight: 400;
		font-size: 0.9rem;
		& > * {
			flex: 1;
			display: flex;
			justify-content: center;
			align-items: center;
			height: 50px;
			border-right: 1px solid white;

			&:last-child {
				border-right: none;
			}
		}
	}
}
</style>