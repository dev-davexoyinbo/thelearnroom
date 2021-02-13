<template>
  <div class="online-class-card">
    <div class="top"></div>
    <div class="bottom">
      <div class="stars-container">
        <p class="star" v-for="i in 5" :key="i" :class="{ active: i <= 3 }">
          <i class="fas fa-star"></i>
        </p>
      </div>
      <div class="title">Lorem ipsum dolor sit amet</div>
      <p class="age-range">Age 14-16</p>
    </div>
    <div class="footer">
      <div class="author">
        <div class="profile-photo"></div>
        <div class="name">John D</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "~assets/styles/variables";

.online-class-card {
  width: 100%;
  box-shadow: -2px 2px 10px rgba($darkBorderGray, 0.15);
  .top {
    height: 150px;
    background: $placeholderGray;
  }
  .bottom {
    padding: 16px;
    .stars-container {
      display: flex;
      margin-bottom: 16px;
      .star {
        color: $placeholderGray;
        &.active {
          color: $starYellow;
        }
      }
    }
    .title {
      margin-bottom: 16px;
      color: black;
      font-size: 1.1rem;
    }
  }
  .footer {
    margin-top: 32px;
    border-top: 1px solid $borderGray;
    padding: 12px 16px;
    .author {
      display: flex;
      align-items: center;
      .profile-photo {
        --size: 30px;
        background-color: $placeholderGray;
        height: var(--size);
        width: var(--size);
        border-radius: 50px;
        overflow: hidden;
        margin-right: 10px;
      }
    }
  }
}
</style>