<template>
  <section id="hero-section" ref="heroSection">
    <div class="content">
      <p class="text-content">Where Kids Explore New Topics & Love to Learn</p>
      <button @click="openJoinModal()">Join For Free</button>
    </div>
  </section>
</template>

<script>
export default {
  mounted() {
    this.$nextTick(() => {
      this.oberserverForNavbar();
    });
  },
  methods: {
    openJoinModal() {
      this.$nuxt.$emit('set-join-modal-state', true)
    },
    oberserverForNavbar() {
      const element = this.$refs.heroSection;

      const homeNavbarHeight = getComputedStyle(element)
        .getPropertyValue("--home-navbar-height")
        .trim();
      const options = {
        rootMargin: `-${homeNavbarHeight}`,
      };

      const callback = (entries, observer) => {
        entries.forEach((entry) => {
          console.log(entry);
          if (entry.isIntersecting) {
            // make navbar transparent
            this.$nuxt.$emit("set-navbar-transparent", true);
          } else {
            //make navbar solid colored
            this.$nuxt.$emit("set-navbar-transparent", false);
          }
        });

        console.log("reached");
      };

      const observer = new IntersectionObserver(callback, options);
      observer.observe(element);
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#hero-section {
  height: var(--viewport-height);
  background-image: url("/images/hero-image-sm.png");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
  background-color: rgba(0, 0, 0, 0.56);
  background-blend-mode: darken;
  padding: 0 var(--body-padding);
  padding-top: 64px;
  color: white;

  display: flex;
  align-items: center;
  justify-content: center;

  @media only screen and (min-width: 768px) {
    background-image: url("/images/hero-image.png");
  }

  .content {
    font-size: 1.5rem;
    font-weight: 500;
    display: flex;
    align-items: center;
    flex-direction: column;
    

    @media only screen and (min-width: 768px) {
      font-size: 2rem;
    }

    .text-content {
      padding-bottom: 2rem;
      text-align: center;
    }

    & > button {
      border: none;
      color: white;
      padding: 12px 24px;
      border-radius: 5px;
      background: $primaryColor;
      outline: none;
      font-weight: 400;
      font-size: 1.1rem;
      cursor: pointer;
      &:active {
        outline: none;
      }
    }
  }
}
</style>