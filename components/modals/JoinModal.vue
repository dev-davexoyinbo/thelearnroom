<template>
  <div ref="modal" id="join-modal" :class="{ open: isOpen, closed: !isOpen }">
    <div class="content">
      <div class="close-button-container">
        <div class="close-button" @click="closeModal()">
          <i class="fas fa-times"></i>
        </div>
      </div>
      <h2 class="heading">Join The LearnRoom For Free</h2>
      <p class="highlight">
        Explore any intrest with 100,000+ classes , pay as low as $10 USD per
        class.
      </p>
      <div class="image-container">
        <img src="/images/join-modal-image.png" alt="" />
      </div>

      <button class="join-button fb">Continue with Facebook</button>
      <button class="join-button email">Signup with email</button>
      <p class="already-have-account">
        Alredy have an account? <a href="#">Log In</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
  mounted() {
    this.$nextTick(() => {
      // this.closeModal()
      this.closeModal();
      this.$nuxt.$on("set-join-modal-state", (state) => {
        if (state) {
          this.openModal();
        } else {
          this.closeModal();
        }
      });
    });
  },
  methods: {
    closeModal() {
      document.scrollingElement.style.overflow = "";
      const modal = this.$refs.modal;

      if (modal.classList.contains("closing"))
        modal.classList.remove("closing");

      modal.classList.add("closing");

      setTimeout(() => {
        this.isOpen = false;
      }, 500);
    },
    openModal() {
      document.scrollingElement.style.overflow = "hidden";
      const modal = this.$refs.modal;
      if (modal.classList.contains("opening"))
        modal.classList.remove("opening");

      modal.classList.add("opening");

      setTimeout(() => {
        if (modal.classList.contains("opening"))
          modal.classList.remove("opening");
        this.isOpen = true;
      }, 500);
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";

@keyframes closing {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

#join-modal {
  display: none;
  align-items: center;
  justify-content: center;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 15;
  background: rgba(#000000, 0.5);

  &.closing {
    opacity: 0;
    animation-name: closing;
    animation-duration: 0.5s;
  }

  &.opening {
    opacity: 1;
    display: flex;
    animation-name: closing;
    animation-duration: 0.5s;
    animation-direction: reverse;
  }

  &.open {
    display: flex;
  }
  .content {
    padding: 16px;
    background: white;
    border-radius: 10px;
    width: 450px;
	max-width: calc(100% - 32px);

	@media only screen and (min-width: 425px) {
		padding: 24px;

	}

    .close-button-container {
      display: flex;
      align-items: center;
      justify-content: flex-end;
      font-size: 1.2rem;

      .close-button {
        padding: 0.5rem;
        transform: translate(0.5rem, -0.5rem);
        cursor: pointer;
      }
    }
    .heading {
      text-align: center;
      font-weight: 600;
      color: $darkColor2;
      font-size: 1.6rem;
      margin-bottom: 8px;
    }

    .heading + .highlight {
      max-width: 80%;
      text-align: center;
      margin-left: auto;
      margin-right: auto;
    }

    .image-container {
      width: 70%;
      margin-left: auto;
      margin-right: auto;
      img {
        width: 100%;
        object-fit: contain;
      }
    }

    .join-button {
      width: 100%;
      margin-bottom: 8px;
      height: 50px;
      border-radius: 5px;
      outline: none;
      border: none;

      font-size: 1.1rem;
	  cursor: pointer;
      &:active {
        outline: none;
      }

      &.fb {
        color: white;
        background: $facebookBlue;
      }

      &.email {
        background: white;
        border: 1px solid $borderGray;
      }
    }

    .already-have-account {
      text-align: center;
      margin-top: 16px;
      a {
        text-decoration: none;
      }
    }
  }
}
</style>