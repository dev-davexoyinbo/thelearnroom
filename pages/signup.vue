<template>
  <div class="auth-page">
    <div class="content">
      <div class="image-container signup">
        <img src="/images/join-modal-image.png" alt="" />
      </div>
      <h2 class="heading">Join The LearnRoom</h2>
      <p class="highlight">Log in for free join now</p>
	  <div class="sized-box-height" style="--height: 24px"></div>
	  <button class="auth-page-button fb">Continue with Facebook</button>
	  <div class="sized-box-height" style="--height: 16px"></div>
	  <button class="auth-page-button">Log In with Email</button>
	  <div class="sized-box-height" style="--height: 24px"></div>
	  <p>Alredy have an accouny? <a href="#"> Log In</a></p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.image-container {
	width: 100%;
	img{
		max-width: 100%;
		object-fit: contain;
	}
}
</style>