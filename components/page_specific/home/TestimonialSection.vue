<template>
  <section id="testimonial-section" class="home-page-section" >
    <h1 class="heading">Testimonial</h1>
    <div class="testimonials-container">
      <div class="angle-container left">
        <button @click="scrollCardsContainer(-1)">
          <i class="fas fa-angle-left"></i>
        </button>
      </div>
      <div class="cards-container" ref="cardsContainer">
        <div class="card" v-for="i in 5" :key="i">
          <div class="profile-photo"></div>
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam non
            eros tellus. Phasellus nec iaculis sapien. Fusce est bibendum
          </div>
          <div class="author">
            <span class="name">john duff {{ i }} </span>
            <span>- Web Designer</span>
          </div>
        </div>
      </div>
      <div class="angle-container right">
        <button @click="scrollCardsContainer(1)">
          <i class="fas fa-angle-right"></i>
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    scrollCardsContainer(val) {
      const mVal = val < 0 ? -1 : 1;
      const cardsContainer = this.$refs.cardsContainer;

      if (cardsContainer.getElementsByClassName("card").length == 0) return;

      const firstCard = cardsContainer.getElementsByClassName("card")[0];
      const width = parseFloat(
        getComputedStyle(firstCard).width.trim().replace(/px$/, "")
      );
      const marginRight = parseFloat(
        getComputedStyle(firstCard).marginRight.trim().replace(/px$/, "")
      );

      let scrollValue = width + marginRight;

      const currentScrollPosition = cardsContainer.scrollLeft;
      let newScrollPosition = currentScrollPosition + scrollValue * mVal;
      newScrollPosition -= newScrollPosition % scrollValue;

      if (mVal < 0) newScrollPosition += scrollValue;

      cardsContainer.scroll(newScrollPosition, 0);
      //   debugger
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#testimonial-section {

  & > .heading {
    color: black;
    font-weight: 400;
    font-size: 1.7rem;
    margin-bottom: 8px;
    text-align: center;
    margin-bottom: 32px;
  }

  .testimonials-container {
    display: grid;
    grid-template-columns: 40px 1fr 40px;
    gap: 10px;
    width: 500px;
    max-width: 100%;
    margin-right: auto;
    margin-left: auto;
    align-items: center;
    justify-content: center;
    .angle-container {
      button {
        background: $neutralHighlight;
        cursor: pointer;
        height: 30px;
        width: 30px;
        border-radius: 50%;
        border: none;
        outline: none;
        &:active {
          outline: none;
        }
      }
    }

    .cards-container {
      display: flex;
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
      .card {
        width: 100%;
        min-width: 100%;
        max-width: 100%;
        margin-right: 16px;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        .profile-photo {
          height: 100px;
          width: 100px;
          border-radius: 50%;
          background: $darkBorderGray;
          margin-bottom: 32px;
        }

        .highlight {
          margin-bottom: 8px;
        }

        .author .name {
          text-transform: uppercase;
          font-weight: 500;
        }
      }
    }
  }
}
</style>