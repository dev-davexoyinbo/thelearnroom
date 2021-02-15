<template>
  <div id="teachers-availability-page">
    <div class="content">
      <div class="page-section">
        <h1 class="h1 heading">Auto-scheduled sections</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
          eiusmod tempor incididunt ut l et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco laboris nisi aliquip
          ex eacommodo consequat. Duis aute irure dolor in reprehenderit in
          voluptatevelit esse dolore eu fugiat nulla pariatur. Excepteursint
          occaecatcupidatat non proident, su <a href="#"> learn more</a>
        </p>
      </div>

      <div class="page-section">
        <h3 class="h3 heading">Schedule availabilty</h3>
        <p>
          Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
          eiusmod tempor incididunt ut l et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco
          <a href="#">Learn More</a>
        </p>
        <div class="sized-box-height" style="--height: 8px"></div>
        <generic-button
          :fontSizeFactor="0.8"
          :sizeFactor="1.2"
          :bgLight="true"
          :textBlack="true"
          >Monthly Available</generic-button
        >
      </div>

      <div class="page-section">
        <h3 class="h3 heading">Exception Date</h3>
        <p>
          Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
          eiusmod tempor incididunt ut l et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco laboris nisi dolore eu
          fugiat nulla pariatur. Excepteursint occaecatcupidatat non proident,
          su
          <a href="#">learn more</a>
        </p>
        <div class="sized-box-height" style="--height: 8px"></div>
        <generic-button
          :fontSizeFactor="0.8"
          :sizeFactor="1.2"
          :bgLight="true"
          :textBlack="true"
          >Add Exception Date</generic-button
        >
      </div>
    </div>
  </div>
</template>

<script>
import GenericButton from "~/components/buttons/GenericButton.vue";
export default {
  components: { GenericButton },
  layout: "teachers",
};
</script>

<style lang="scss">
@import "~assets/styles/variables";

#teachers-availability-page {
  padding: 24px var(--body-padding);
  font-size: 0.9rem;
  a {
    color: $primaryColor;
    text-decoration: none;
  }

  .content {
    max-width: 600px;
  }
  .heading {
    &.h1 {
      margin-bottom: 12px;
    }

    &.h2 {
      margin-bottom: 10px;
    }
    &.h3 {
      margin-bottom: 8px;
    }
  }

  .page-section {
    margin-bottom: 32px;
  }
}
</style>