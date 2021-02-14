<template>
  <section class="interested-section">
      <div class="interested-box">
        <h1 class="heading">Intrested in something particular</h1>
        <button class="submit-topic-button">Submit Topic</button>
      </div>
    </section>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import '~assets/styles/variables';

.interested-section {
    .interested-box {
      text-align: center;
      padding: 48px 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      background: $offWhite;
      border: 1px solid #BAB9B9;
      border-radius: 5px;

      .heading{
        display: inline-block;
        font-size: 1.7rem;
        color: black;
        margin-bottom: 16px;
        font-weight: 400;
      }

      .submit-topic-button {
        color: white;
        border: none;
        outline: none;
        background: $primaryColor;
        padding-left: 16px;
        padding-right: 16px;
        height: 30px;
        border-radius: 5px;
        cursor: pointer;
        &:active {
          outline: none;
        }
      }
    }
  }
</style>