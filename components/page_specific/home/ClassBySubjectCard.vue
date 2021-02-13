<template>
  <div class="class-by-subject-card">
    <h1 class="heading"><i :class="data.iconClass"></i> {{ data.heading }}</h1>
    <div class="classes-container">
      <p class="class" v-for="c in data.classes" :key="c.title">
        <a :href="c.link">{{ c.title }}</a>
      </p>
    </div>
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

.class-by-subject-card {
  background: white;
  border-radius: 5px;
  padding: 16px;
  & > .heading {
    font-weight: 400;
    font-size: 1.2rem;
  }

  .classes-container {
    display: flex;
    flex-wrap: wrap;
    font-size: 0.9rem;
    .class {
      padding: 4px 8px;
      border-right: 1px solid $borderGray;

      padding-left: 0;
      margin-right: 8px;
      &:last-child {
        padding-right: 0;
        border-right: none;
      }
      a {
        color: $primaryColor;
        text-decoration: none;
      }
    }
  }
}
</style>