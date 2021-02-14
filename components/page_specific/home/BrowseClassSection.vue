<template>
  <div class="browse-class-section home-page-section">
	  <h1 class="heading">Browse Classes</h1>
	  <div class="cards-container">
		  <div class="single-card-container" v-for="i in 3" :key="i">
			  <browse-class-card />
		  </div>
	  </div>
  </div>
</template>

<script>
import BrowseClassCard from '~/components/page_specific/home/BrowseClassCard.vue'
export default {
  components: { BrowseClassCard },

}
</script>

<style lang="scss">
.browse-class-section {
	.heading {
      color: black;
      font-weight: 400;
      font-size: 1.7rem;
      margin-bottom: 16px;
	  text-align: center;
    }

	.cards-container {
		display: grid;
		grid-template-columns: 1fr;
		gap: 16px;
		row-gap: 32px;

		@media only screen and (min-width: 768px){
			grid-template-columns: repeat(3, 1fr);
		}

		@media only screen and (min-width: 1024px){
			gap: 32px;
		}
	}
}
</style>