<template>
  <div class="teachers-signup-card">
    <h3 class="h3 heading">Join the New & Future The LearRoom Teachers Group</h3>
    <div class="description">
      Lorem ipsum dolor sit sit gmet Lorem ipsum dolor sit elitamet Lorem ipsum
      dolor sit as amet consectetur adipiscing as elit Nam non eros tellus.
    </div>
    <generic-button
      :noBorder="true"
      :bgLight="true"
      :textPrimary="true"
      :withShadow="true"
    >
      Sign up to teach
    </generic-button>

    <div class="box"></div>
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

.teachers-signup-card {
  padding: 16px;
  background: $primaryColor-dark-2;
  color: white;
  border-radius: 5px;

  .heading {
    color: white;
  }

  .description {
    font-size: 0.9rem;
    margin: 32px 0;
  }

  .box{
    width: 100%;
    height: 200px;
    background: $placeholderGray;
    margin-top: 32px;
  }
}
</style>