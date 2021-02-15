<template>
  <div id="teachers-classes-page">
    <div class="header-section">
      <h1 class="h1 heading">
        My Classes &nbsp;
        <select class="category-select" name="" id="">
          <option value="">All</option>
        </select>
      </h1>
      <p class="highlight">
        We will send you an Email to notify your followers.
        <a href="#">Share your profile</a>
      </p>
    </div>
    <div class="">
      <div class="add-class-button-container">
        <generic-button
          :primary="true"
          :noBorder="true"
          :sizeFactor="1.2"
          :fontSizeFactor="0.9"
          >Add a class</generic-button
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

#teachers-classes-page {
  padding: 24px var(--body-padding);
  .header-section {
    .heading {
      display: flex;
      justify-content: center;
      align-items: center;
      .category-select {
        height: 30px;
        width: 80px;
        border: 1px solid $borderGray;
        border-radius: 5px;
      }
    }
    .highlight {
      text-align: center;
      max-width: 500px;
      font-size: 0.9rem;
      margin-right: auto;
      margin-left: auto;
      margin-top: 16px;
      margin-bottom: 16px;
    }
    a {
      color: $primaryColor;
      text-decoration: none;
    }
  }

  .add-class-button-container {
    display: flex;
    justify-content: center;
  }
}
</style>