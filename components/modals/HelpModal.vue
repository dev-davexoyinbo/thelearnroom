<template>
  <div ref="modal" id="help-modal" :class="{ open: isOpen, closed: !isOpen }">
    <div class="content">
      <div class="header">
        <div class="logo-container">
          <img src="/images/logo-white.png" alt="" />
        </div>
        <div class="close-button-container">
          <div class="close-button" @click="closeModal()">
            <i class="fas fa-times"></i>
          </div>
        </div>
        <h3 class="heading">Hi There <span class="emoji"> &#128075;</span></h3>
      </div>
      <div class="body">
        <div class="body-header">
          <h3 class="heading">Start a conversation</h3>
          <div class="body-header-content">
            <div class="stacked-circles-container">
              <div class="stacked-circle"></div>
              <div class="stacked-circle"></div>
              <div class="stacked-circle"></div>
            </div>
            <div class="details">
              <p>lorem ipsum is simply</p>
              <p style="color: black">
                <i class="far fa-clock"></i> Later Today
              </p>
            </div>
          </div>
          <button class="body-header-button">
            <i class="fas fa-envelope"></i> Send us a message
          </button>
        </div>
        <div class="help-item" v-for="i in 4" :key="i">
          <div class="question">
            Lorem Ipsum is simply dummy text of the printing lorem
          </div>
          <div class="response">
            Lorem Ipsum is simply dummy text of the printing lorem
          </div>
        </div>
      </div>
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
      this.$nuxt.$on("set-help-modal-state", (state) => {
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

#help-modal {
  display: none;
  //   align-items: center;
  justify-content: center;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 15;
  background: rgba(#000000, 0.5);
  overflow: hidden;
  overflow-y: auto;
  padding: 32px 16px;

  @media only screen and (min-width: 435px) {
    justify-content: flex-end;
  }

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
  & > .content {
    --padding: 16px;
    --heading-inner-space: 50px;
    background: white;
    border-radius: 10px;
    width: 320px;
    max-width: 100%;
    height: fit-content;
    overflow: hidden;
    border: 1px solid #707070;

    .header {
      background: $primaryColor-medium;
      padding: var(--padding);
      padding-bottom: calc(var(--padding) + var(--heading-inner-space));
      position: relative;
      color: white;
      .logo-container {
        height: 15px;
        max-width: calc(100% - 32px);
        img {
          object-fit: contain;
          height: 100%;
          max-height: 100%;
          max-width: 100%;
        }
      }

      .close-button-container {
        position: absolute;
        top: var(--padding);
        right: var(--padding);
        cursor: pointer;
      }

      .heading {
        margin-top: 16px;
        font-weight: 400;
        font-size: 1.8rem;
      }
    }
    .body {
      padding: var(--padding);
      padding-top: 0;
      margin-top: calc(-1 * var(--heading-inner-space));
      position: relative;
      z-index: 2;

      & > * {
        box-shadow: 0px 2px 10px 0px rgba($darkBorderGray, 0.3);
      }

      //body header
      .body-header {
        background: white;
        border-radius: 5px;
        padding: 16px;
        border: 1px solid $borderGray;
        margin-bottom: 16px;
        & > .heading {
          font-weight: 400;
          color: black;
          margin-bottom: 8px;
        }

        .body-header-content {
          display: flex;
          align-items: center;
          margin-bottom: 8px;
          .stacked-circles-container {
            --stacked-circle-size: 50px;
            --stacked-circle-spacing: 15px;
            margin-right: 10px;
            width: calc(
              var(--stacked-circle-size) +
                calc(var(--stacked-circle-spacing) * 2)
            );
            height: var(--stacked-circle-size);
            position: relative;
            .stacked-circle {
              height: var(--stacked-circle-size);
              width: var(--stacked-circle-size);
              border-radius: 50%;
              position: absolute;
              left: 0;
              top: 0;
              background: $backgroundGray;
              border: 1px solid $darkBorderGray;

              &:nth-child(2) {
                left: var(--stacked-circle-spacing);
              }
              &:nth-child(3) {
                left: calc(var(--stacked-circle-spacing) * 2);
              }
            }
          }

          .details {
            font-size: 0.9rem;
          }
        }

        .body-header-button {
          height: 30px;
          background: $primaryColor-medium;
          color: white;
          padding-left: 16px;
          padding-right: 16px;
          border-radius: 5px;
          border: none;
          outline: none;
          cursor: pointer;
          &:active {
            outline: none;
          }
        }
      }

      //Help item
      .help-item {
        border-radius: 5px;
        border: 1px solid $borderGray;
        border-top: 2px solid $primaryColor-medium;
        padding: 16px;
        font-size: 0.9rem;
        margin-bottom: 10px;

        &:last-child {
          margin-bottom: 0;
        }
        .question {
          color: $primaryColor-medium;
          margin-bottom: 4px;
        }
      }
    }
  }
}
</style>