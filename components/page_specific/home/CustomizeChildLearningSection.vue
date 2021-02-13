<template>
  <section class="customize-child-learning-section">
    <h1 class="heading">Customise Your Child’s Learning</h1>
    <div class="cards-container">
      <div
        class="single-card-container"
        v-for="(datum, i) in customizeChildLearningData"
        :key="i"
      >
        <customize-child-learning-card :data="datum" />
      </div>
    </div>
  </section>
</template>

<script>
import CustomizeChildLearningCard from "./CustomizeChildLearningCard.vue";
export default {
  components: { CustomizeChildLearningCard },
  data() {
    return {
      customizeChildLearningData: [
        {
          img: "/images/join-modal-image.png",
          heading: "Discover",
          highlight:
            "From mathematics to piano to Financial Literacy to Animation, the LearnRoom provides your kids with an insight to multiple different fields and avariety of ideas with exposureto a board range of different topics of 5000+ classes",
        },
        {
          img: "/images/study.png",
          heading: "Learn with peers",
          highlight:
            "Grow your learner’s confidence in and out of the classroom with live video classes that meet in small groups",
        },
        {
          img: "/images/encourage-teaching.png",
          heading: "Encouraging Teachers",
          highlight:
            "All teachers and instructors are verified by your in-house team and consist of accredited professionals, scientists, specialists, inventors and inspired adults with an expertise to share. Interested in becoming a teacher? Apply here",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.customize-child-learning-section {
  margin-top: 16px 0;
  padding: 32px var(--body-padding);

  .heading {
    color: black;
    font-weight: 400;
    font-size: 1.7rem;
    margin-bottom: 8px;
    text-align: center;
    margin-bottom: 32px;
  }

  .cards-container {
    display: grid;
    grid-template-columns: 1fr;
	gap: 16px;
	row-gap: 32px;

	@media only screen and (min-width: 768px) {
		grid-template-columns: repeat(3, 1fr);
	}
	@media only screen and (min-width: 1024px){

		gap: 32px;
	}
  }
}
</style>