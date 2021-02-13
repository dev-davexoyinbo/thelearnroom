<template>
  <div id="meet-our-teacher-section">
    <h1 class="heading">Meet Our Teachers</h1>
    <div class="cards-container">
      <div class="single-card-container" v-for="i in 4" :key="i">
        <home-teacher-card />
      </div>
    </div>
    <div class="interested-in-teaching-subsection">
      <h2 class="sub-heading">Interested in teaching?</h2>
      <div class="highlight">Join our inspiring community of teachers</div>
      <div class="button-container">
        <button>Join For Free</button>
      </div>
    </div>
  </div>
</template>

<script>
import HomeTeacherCard from "./HomeTeacherCard.vue";
export default {
  components: { HomeTeacherCard },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#meet-our-teacher-section {
  margin-top: 16px 0;
  padding: 32px var(--body-padding);
  border-top: 1px solid $borderGray;

  & > .heading {
    color: black;
    font-weight: 400;
    font-size: 1.7rem;
    margin-bottom: 8px;
    text-align: center;
    margin-bottom: 32px;
  }

  .sub-heading {
    color: black;
    font-weight: 400;
    font-size: 1.5rem;
    text-align: center;
    margin-bottom: 8px;
  }

  .cards-container {
    display: grid;
    grid-template-columns: 1fr;
    gap: 16px;
    row-gap: 32px;
    margin-bottom: 32px;

    @media only screen and (min-width: 425px) {
      grid-template-columns: repeat(2, 1fr);
    }

    @media only screen and (min-width: 768px) {
      grid-template-columns: repeat(4, 1fr);
    }

    @media only screen and (min-width: 1024px) {
      gap: 32px;
    }
  }

  .interested-in-teaching-subsection {
    background: $offWhite;
    border: 1px solid #bab9b9;
    border-radius: 5px;
    padding: 16px;
    .highlight {
      text-align: center;
    }
    .button-container {
      display: flex;
      align-items: center;
      justify-content: center;
	  margin-top: 12px;
	  button {
		  color: white;
		  border: none;
		  outline: none;
		  background: $primaryColor;
		  padding-left: 16px;
		  padding-right: 16px;
		  height: 30px;
		  border-radius: 5px;
		  &:active{
			  outline: none;
		  }
	  }
    }
  }
}
</style>