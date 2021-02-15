<template>
  <div id="teachers-section-page">
    <p>
      Need some help picking a time? <a href="#">Click here</a> to guidance on
      when to schedule.
    </p>
    <div class="buttons-container">
      <generic-button
        :sizeFactor="1.2"
        :fontSizeFactor="0.8"
        :noBorder="true"
        :primary="true"
        >Schedule a section</generic-button
      >
      <generic-button
        :bgLight="true"
        :sizeFactor="1.2"
        :fontSizeFactor="0.8"
        :textPrimary="true"
        >Download all CSV...</generic-button
      >
      <generic-button
        :bgLight="true"
        :sizeFactor="1.2"
        :fontSizeFactor="0.8"
        :textPrimary="true"
        >Download Ongoing Section as CSV...</generic-button
      >
    </div>

    <div class="tuning-section">
      <select name="" id="" class="tuning-select">
        <option value="">Active</option>
      </select>
      <span class="some-text">Section by start time</span>
      <div class="show-enroll">
        <i class="fas fa-check-circle icon"></i>
        <span>Show Classes with no Enroll </span>
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
#teachers-section-page {
  padding: 24px var(--body-padding);
  a {
    color: $primaryColor;
    text-decoration: none;
  }

  .buttons-container {
    display: flex;
    flex-wrap: wrap;
    margin-top: 16px;
    margin-bottom: 8px;
    & > * {
      margin-bottom: 8px;
      margin-right: 16px;
    }
  }

  .tuning-section {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    margin-top: 32px;
    & > * {
      margin-bottom: 8px;
    }
    .tuning-select {
      background: white;
      outline: none;
      border: 1px solid $borderGray;
      border-radius: 3px;
      width: 100px;
      height: 30px;
      padding-left: 5px;
      font-size: 0.9rem;
      box-shadow: -2px 2px 1px rgba($borderGray, 0.8);
      &:active {
        outline: none;
      }
    }
    .some-text {
      font-size: 0.9rem;
      margin-right: 24px;
      margin-left: 8px;
    }

    .show-enroll {
      display: flex;

      align-items: center;
      font-size: 1.2rem;
      color: black;
      .icon {
        margin-right: 6px;
        color: $primaryColor;
      }
    }
  }
}
</style>