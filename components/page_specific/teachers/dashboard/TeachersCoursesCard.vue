<template>
  <div class="teachers-courses-card">
    <div class="icon-column-container">
      <div class="icon-container">
        <i class="fas fa-angle-right"></i>
      </div>
    </div>
    <div class="content">
      <h4 class="h4 heading">Complete The LearnRoom 101</h4>
      <div class="description">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit Nam non eros
        tellus. Phasellus nec iaculis sapien. Fusce est bibendum
      </div>
      <div class="footer">
        <generic-button
          :noBorder="true"
          :withShadow="true"
          :primaryDark="true"
          :sizeFactor="0.9"
          >The learnroom</generic-button
        >
      </div>
    </div>
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

.teachers-courses-card {
  display: grid;
  grid-template-columns: 20px 1fr;
  gap: 16px;

  &:last-child {
    .content {
      border-bottom: none !important;
    }
  }

  & > * {
    padding: 16px 0;
  }

  .icon-column-container {
    .icon-container {
      height: 25px;
      width: 25px;
      border-radius: 50%;
      background: $neutralHighlight;
      border: 1px solid $borderGray;
      color: black;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }

  .content {
    border-bottom: 1px solid $borderGray;
    .heading {
      margin-bottom: 12px;
    }
    .description {
      font-size: 0.9rem;
      margin-bottom: 8px;
      max-width: 400px;
    }
  }
}
</style>