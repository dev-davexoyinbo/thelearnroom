<template>
  <div id="students-find-class-page">
    <header class="header">
      <div class="bread-crumb">
        <i class="fas fa-angle-left"></i> <span>Home</span>
      </div>
      <h1 class="heading">Find Classes</h1>
    </header>
    <section class="search-section">
      <div class="form">
        <input type="text" class="form-control" placeholder="Search" />
      </div>
      <div class="buttons-container">
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true" :sizeFactor="0.8" 
            >Any Date</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true" :sizeFactor="0.8" 
            >Any time</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true" :sizeFactor="0.8" >Any age</generic-button>
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true" :sizeFactor="0.8" 
            >Any subject</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true" :sizeFactor="0.8" 
            >Any format</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true" :sizeFactor="0.8" 
            >Any length</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true" :sizeFactor="0.8" >More</generic-button>
        </div>
      </div>
    </section>
	<section class="sort-section tlr--d-flex tlr--justify-content-flex-end tlr--align-items-center">
		<span class="sort-text">Sort: </span>
		<generic-button :sizeFactor="0.8" >Starting soon</generic-button>
	</section>
	<section class="class-listing-section">
		<div class="class-strip-container"  v-for="i in 4" :key="i">

		<class-strip />
		</div>
	</section>

	<div class="interested-in-something-container">
		<interested-in-something-section />
	</div>
  </div>
</template>

<script>
import GenericButton from "~/components/buttons/GenericButton.vue";
import ClassStrip from '~/components/cards/ClassStrip.vue';
import InterestedInSomethingSection from '~/components/InterestedInSomethingSection.vue';
export default {
  components: { GenericButton, ClassStrip, InterestedInSomethingSection },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#students-find-class-page {
  .form {
	  padding: 2px;
	  margin-top: 0;
	  margin-bottom: 4px;
    .form-control {
      height: 25px;
      font-size: 0.8rem;
	  margin-bottom: 0;
    }
  }
  .header {
    padding: 8px var(--body-padding);
    .bread-crumb {
      font-size: 0.8rem;
      margin-bottom: 4px;
    }

    .heading {
      margin-bottom: 0;
      color: black;
      font-weight: 1rem;
    }
  }

  //Search section
  .search-section {
    background: $offWhite;
    padding: 16px var(--body-padding);
    .buttons-container {
      display: flex;
      flex-wrap: wrap;

	  .single-button-container {
		  margin-right: 10px;
		  margin-bottom: 4px;
		  &:last-child {
			  margin-right: 0;
		  }
	  }
    }
  }

  .sort-section {
	  padding: 8px var(--body-padding);
	  padding-top: 16px;
	  font-size: 0.8rem;
	  .sort-text {
		  margin-right: 10px;
	  }
  }

  .class-listing-section {
	  padding: 16px var(--body-padding);
	  padding-top: 0;

	//   .class-strip-container {
	// 	  margin-bottom: 32px;
	// 	  &:last-child {
	// 		  margin-bottom: 0;
	// 	  }
	//   }
  }

  .interested-in-something-container {
	  padding: 32px var(--body-padding);
  }
}
</style>