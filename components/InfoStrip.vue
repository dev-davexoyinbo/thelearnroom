<template>
  <div ref="infoStrip" class="info-strip" :class="{'stick-top': stickTop}">
    <div class="info-item video-offer" :class="{ hide: !videoOffer }">
      <p>
        The LearnRoom offers <a href="#">video chat classes</a> by inspiring
        teachers.
      </p>
    </div>
    <div class="info-item confirm-email" :class="{ hide: !confirmEmail }">
      <p>Confirm your Email by clicking link <a href="">Resend</a></p>
    </div>

    <div
      class="info-item large welcome-message"
      :class="{ hide: !showWelcomeMessage }"
    >
      <p>Welcome!</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    videoOffer: {
      default: false,
    },
    confirmEmail: {
      default: false,
    },
    welcomeMessage: {
      default: false,
    },
    welcomeMessageDuration: {
      default: 5000,
    },
    stickTop : {
      default: false
    }
  },
  data() {
    return {
      showWelcomeMessage: false,
    };
  },
  mounted() {
    this.heightChangeHooks();

    if (this.welcomeMessage) {
      this.showWelcomeMessage = true;
      setTimeout(() => {
        // TODO: Change the value of the next line to false
        this.showWelcomeMessage = false;
      }, this.welcomeMessageDuration);
    }
  },
  updated() {
    this.heightChangeHooks();
  },
  beforeDestroy() {
    document.documentElement.style.setProperty("--info-strip-height", "0px");
  },
  methods: {
    heightChangeHooks() {
      const infoStrip = this.$refs.infoStrip;
      const height = getComputedStyle(infoStrip).height;

      document.documentElement.style.setProperty("--info-strip-height", height);
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
.info-strip {
  position: sticky;
  top: var(--infostrip-stick-value, var(--global-navbar-height));
  z-index: 9;
  box-shadow: 0px 3px 10px rgba($darkColor, 0.18);

  &.stick-top {
    --infostrip-stick-value: 0;
  }

  .hide {
    display: none !important;
  }

  .info-item {
    background: white;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 6px var(--body-padding);
    font-size: 0.85rem;
    text-align: center;

    &.large {
      height: 70px;
    }

    a {
      color: $primaryColor;
    }
  }

  .video-offer {
    background: $primaryColor;

    color: white;

    a {
      color: white;
    }
  }

  .confirm-email {
    background: #fafdd6;
    color: black;
  }

  .welcome-message {
    color: white;
    background: #0f3063;
    font-size: 1.3rem;
    font-weight: 500;
  }
}
</style>