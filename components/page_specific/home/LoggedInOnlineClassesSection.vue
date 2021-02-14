<template>
  <section class="logged-in-online-classes-section home-page-section">
    <div class="info-section">
      <h1 class="heading"><slot name="header">Placeholder Header</slot></h1>
    </div>
    <div class="online-class-cards-container">
      <div class="card-container" v-for="i in 4" :key="i">
        <online-class-card />
      </div>
    </div>
  </section>
</template>

<script>
import OnlineClassCard from "~/components/cards/OnlineClassCard.vue";
export default {
  components: { OnlineClassCard },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";

.logged-in-online-classes-section {
  padding-left: 0 !important;
  padding-right: 0 !important;

  @media only screen and (min-width: 768px) {
    padding-left: var(--body-padding) !important;
    padding-right: var(--body-padding) !important;
  }

  a {
    color: $primaryColor;
    text-decoration: none;
  }
  .info-section {
    text-align: center;
    margin-bottom: 16px;
    padding-left: var(--body-padding);
    padding-right: var(--body-padding);
    @media only screen and (min-width: 768px) {
      padding-left: 0;
      padding-right: 0;
    }
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

  .online-class-cards-container {
    --item-count: 1;
    --margin-right: 16px;

    --unclear-card-width: calc(100% / var(--item-count));

    --card-width: calc(var(--unclear-card-width) - var(--margin-right));

    display: flex;
    width: 100%;
    overflow-x: auto;
    padding-left: var(--body-padding);
    padding-right: var(--body-padding);
    padding-bottom: 16px;

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

    &::after {
      content: "";
      display: flex;
      width: 1px;
      min-width: 1px;
      max-width: 1px;
      margin-left: var(--margin-right);
    }

    @media only screen and (min-width: 425px) {
      --item-count: 2;
    }

    @media only screen and (min-width: 768px) {
      display: grid;
      overflow: unset;
      padding: 0;
      grid-template-columns: 1fr;
      gap: 16px;
      row-gap: 32px;
      grid-template-columns: repeat(2, 1fr);
      &::after {
        display: none;
      }
    }

    @media only screen and (min-width: 1024px) {
      grid-template-columns: repeat(4, 1fr);
      gap: 32px;
    }

    .card-container {
      width: var(--card-width);
      max-width: var(--card-width);
      min-width: var(--card-width);
      margin-right: var(--margin-right);

      @media only screen and (min-width: 768px) {
        width: unset;
        max-width: unset;
        min-width: unset;
        margin-right: unset;
      }
    }
  }
}
</style>