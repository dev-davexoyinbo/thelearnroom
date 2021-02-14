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
          <generic-button :gray="true" :noBorder="true"
            >Any Date</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true"
            >Any tate</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true">Any age</generic-button>
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true"
            >Any subject</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true"
            >Any format</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true"
            >Any length</generic-button
          >
        </div>
        <div class="single-button-container">
          <generic-button :gray="true" :noBorder="true">More</generic-button>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import GenericButton from "~/components/buttons/GenericButton.vue";
export default {
  components: { GenericButton },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#students-find-class-page {
  .form {
	  padding: 2px;
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
		  &:last-child {
			  margin-right: 0;
		  }
	  }
    }
  }
}
</style>