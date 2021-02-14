<template>
  <div class="class-strip">
    <div class="image-container">
      <img src="" alt="" class="image" />
    </div>
    <div class="content">
      <h1 class="heading">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit Nam non eros
        tellus. Phasellus
      </h1>
      <span class="author">john D- WebDesigner</span>
      <div class="description">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
        eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis ipsum
        suspendisse ultrices gravida. Risus commodo viverra maecenas accumsan
        lacus vel facilisis.
      </div>
      <div class="criteria">
        <div class="age">Age 14 - 16</div>
        <div class="frequency">Meet once per week</div>
      </div>
    </div>
    <div class="like-container">
      <i class="far fa-heart"></i>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "~assets/styles/variables";

.class-strip {
  display: grid;
  grid-template-columns: 80px 1fr max-content;
  gap: 8px;
  padding: 24px 0;
  border-top: 1px solid $borderGray;
  width: 100%;
  overflow: hidden;

  @media only  screen and (min-width: 425px) {
    gap: 16px;
    grid-template-columns: 100px 1fr max-content;
  }

  @media only  screen and (min-width: 768px) {
    gap: 24px;
    grid-template-columns: 150px 1fr max-content;
  }

  @media only  screen and (min-width: 768px) {
    gap: 32px;
    grid-template-columns: 200px 1fr max-content;
  }
  .image-container {
    img {
      width: 100%;
      height: 70px;
      object-fit: cover;
      background-color: $placeholderGray;
    }
  }

  .content {
    max-width: 800px;
    font-size: 0.9rem;
    .heading {
      color: $primaryColor;
      font-weight: 400;
      font-size: 1.3rem;
      margin-bottom: 2px;
    }
    .author {
      display: block;
      margin-bottom: 12px;
    }
    .description {
      margin-bottom: 4px;
    }
    .criteria {
      display: grid;
      grid-template-columns: max-content 1fr;
      gap: 32px;
      font-size: 1rem;
    }
  }
}
</style>