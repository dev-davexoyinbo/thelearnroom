<template>
  <div class="auth-page">
    <div class="content">
      <div class="heading">Set a new password</div>
      <p class="highlight">
        Lorem ipsum dolor sit amet Lorem ipsum dolor sit ametL orem ipsum dolor
        sit amet
      </p>
      <form action="" class="form">
        <input type="email" class="form-control" placeholder="Email" />
        <div class="set-password-button-container">

        <button class="set-password-button">Continue</button>
        </div>
      </form>
      <div class="sized-box-height" style="--height: 4px"></div>
	  <p>You can also <a href="#">Log In</a>  or <a href="#">Sign in</a></p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import '~assets/styles/variables';
.set-password-button-container {
  display: flex;
  align-items:center;
  justify-content: center;
}
.set-password-button {
  height: 40px;
  border: 1px solid #C4C4C4;
  outline: none;
  border-radius: 5px;
  background: white;
  padding-left: 24px;
  padding-right: 24px;
  cursor: pointer;
  background: #EFEFEF;
  color: #C4C4C4;
  &:active {
    outline: none;
  }
}


</style>