<template>
  <section id="online-classes-section">
    <div class="info-section">
      <h1 class="heading">Live Online Classes & Courses</h1>
      <p class="highlight">
        Explore multiple intrests over live video chat with award winning
        teachers and instructors. Discover fun, social, interactive and safe
        learning experience for kids aged 6- 18 led by passionate teachers.
        classes from £10.
      </p>
      <p class="highlight"><a href="#">How it works</a></p>
    </div>
    <div class="online-class-cards-container">
      <div class="card-container" v-for="i in 4" :key="i">
        <online-class-card />
      </div>
    </div>
  </section>
</template>

<script>
import OnlineClassCard from './OnlineClassCard.vue';
export default {
  components: { OnlineClassCard },};
</script>

<style lang="scss">
@import '~assets/styles/variables';

#online-classes-section {
  padding: 16px var(--body-padding);
  a {
    color: $primaryColor;
    text-decoration: none;
  }
  .info-section {
    text-align: center;
    margin-bottom: 32px;
    .heading {
      color: black;
      font-weight: 400;
      font-size: 1.7rem;
      margin-bottom: 8px;
    }
    .highlight {
      max-width: calc(500px + 32px);
      padding: 0 16px;
      font-size: 0.9rem;
      margin-right: auto;
      margin-left: auto;
      margin-bottom: 4px;
      &:last-child {
        margin-bottom: 0;
      }
    }
  }

  .online-class-cards-container{
    display: grid;
    grid-template-columns: 1fr;
    gap: 16px;
    row-gap: 32px;

    @media only screen and (min-width: 620px) {
      grid-template-columns: repeat(2, 1fr);
    }

    @media only screen and (min-width: 1024px) {
      grid-template-columns: repeat(4, 1fr);
      gap: 32px;

    }
  }
}
</style>