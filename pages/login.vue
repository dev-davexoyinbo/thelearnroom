<template>
  <div class="auth-page">
    <div class="content">
      <h2 class="heading">Log In</h2>
      <div class="sized-box-height" style="--height: 4px"></div>
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
        <a href="/set-password" class="forgot-password" @click.prevent="goToPage('/set-password')">Forgot your password?</a>
        <button type="submit" class="auth-page-button email">Log In with Email</button>
      </form>
      <p>Don’t have The LearnRoom account?  <a href="/signup" @click.prevent="goToPage('/signup')"> Sign Up</a></p>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'auth',
  methods: {
    goToPage(path){
      event.preventDefault()
      this.$nuxt.$router.push(path)
    }
  }
};
</script>

<style lang="scss">
</style>