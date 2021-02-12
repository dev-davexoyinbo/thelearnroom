<template>
  <div class="auth-page">
    <div class="content">
      <h2 class="heading">Log In</h2>
      <button class="auth-page-button fb">Continue with Facebook</button>
      <p class="or">or</p>
      <form action="" class="form">
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" class="form-control" placeholder="Email">
        </div>
        <div class="form-group">
          <label for="password">Password</label>
          <input type="password" class="form-control" placeholder="*********">
        </div>
        <a href="#" class="forgot-password">Forgot your password?</a>
        <button type="submit" class="auth-page-button email">Log In with Email</button>
      </form>
      <p>Don’t have The LearnRoom account?  <a href="#"> Sign Up</a></p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
</style>