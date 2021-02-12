<template>
  <footer id="footer">
    <div class="column">
      <div class="logo-container">
        <img src="/images/logo.png" alt="" />
      </div>
      <p>Lorem Ipsum is simply dummy text of the printing lorem</p>
      <div class="social-media-section">
        <div class="item"><i class="fab fa-facebook-f"></i></div>
        <div class="item"><i class="fab fa-pinterest-p"></i></div>
        <div class="item"><i class="fab fa-twitter"></i></div>
        <div class="item"><i class="fab fa-google-plus-g"></i></div>
        <div class="item"><i class="fab fa-instagram"></i></div>
      </div>
      <p>2021 The LearnRoom ©</p>
    </div>
    <div class="column">
      <div class="heading">learn</div>
      <div class="links">
        <a href="#" class="link-item">Terms and Conditions</a>
        <a href="#" class="link-item">About Us</a>
        <a href="#" class="link-item">Secure Payment</a>
        <a href="#" class="link-item">Contact Us</a>
        <a href="#" class="link-item">Site-map</a>
      </div>
    </div>
    <div class="column">
      <div class="heading">About Us</div>
      <div class="links">
        <a href="#" class="link-item">Addresses</a>
        <a href="#" class="link-item">Credit Slip</a>
        <a href="#" class="link-item">Orders</a>
        <a href="#" class="link-item">Personal Information</a>
        <a href="#" class="link-item">Rewards</a>
      </div>
    </div>
    <div class="column">
      <div class="heading">Support</div>
      <div class="links">
        <a href="#" class="link-item">Help</a>
        <a href="#" class="link-item">Safety</a>
        <a href="#" class="link-item">Contact Us</a>
        <a href="#" class="link-item">Site-map</a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "~assets/styles/variables";

#footer {
  padding: 32px var(--body-padding);
  padding-bottom: 48px;

  display: grid;
  grid-template-columns: repeat(1, 1fr);
  font-size: 0.9rem;
  row-gap: 48px;

  

  & > .column {
    --padding-size: 16px;
    &:first-child {
      padding-left: 0;
      border-left: none;
      // grid-column: span 3;
    }
    .logo-container {
      margin-bottom: 16px;
      img {
        max-height: 20px;
        max-width: 100%;
        object-fit: contain;
      }
    }

    .logo-container + p {
      max-width: 250px;
    }

    .social-media-section {
      display: flex;
      color: $darkColor;
      font-size: 12px;
      margin-top: 24px;
      margin-bottom: 16px;
      & > .item {
        margin-right: 6px;
        display: flex;
        align-items: center;
        justify-content: center;
        height: 25px;
        width: 25px;
        border: 1px solid $darkColor;
        border-radius: 50%;

        &:last-child {
          margin-right: 0;
        }
      }
    }

    .heading {
      text-transform: uppercase;
      font-weight: 500;
      margin-bottom: 8px;
      color: black;
      font-size: 1.1rem;
    }

    .links {
      display: flex;
      flex-direction: column;
      .link-item {
        color: $textColor;
        text-decoration: none;
        margin-bottom: 8px;
        &:last-child {
          margin-bottom: 0;
        }
      }
    }
  }

  @media only screen and (min-width: 425px) {
    grid-template-columns: repeat(3, 1fr);

    & > .column {
      border-left: 1px solid $neutralHighlight;
      padding: var(--padding-size);

      &:first-child{
        grid-column: span 3;
        border-left: none;
        padding-left: 0;
        padding-right: 0;
      }
      &:nth-child(2) {
        border-left: none;
        padding-left: 0;

      }
      &:nth-child(4) {
        padding-right: 0;
      }
    }
  }

  @media only screen and (min-width: 768px) {
    grid-template-columns: repeat(4, 1fr);
    & > .column {
      &:first-child{
        grid-column: span 1;
      
        padding-right:var(--padding-size);
      }
      &:nth-child(2) {
        border-left: 1px solid $neutralHighlight;
        padding-left: var(--padding-size);;

      }
    }
  }
}
</style>