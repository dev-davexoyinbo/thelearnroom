<template>
  <div class="customize-child-learning-card">
    <div class="image-container">
      <img :src="data.img" alt="" />
    </div>
    <h1 class="heading">{{ data.heading }}</h1>
    <p class="highlight">{{ data.highlight }}</p>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      required: true,
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";

.customize-child-learning-card {
  text-align: center;
//   padding: 16px;
  .image-container {
    padding: 8px;
    border: 1px solid rgba($borderGray, 0.8);
    max-width: 100%;
    height: 180px;
    img {
      height: 100%;
      max-width: 100%;
      object-fit: contain;
    }
  }

  .heading {
    margin-top: 16px;
    margin-bottom: 4px;
    font-size: 1.3rem;
    font-weight: 500;
	color: $textColor;
  }

  .highlight {
    font-size: 0.9rem;
  }
}
</style>