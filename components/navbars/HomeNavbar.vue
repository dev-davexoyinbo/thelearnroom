<template>
  <nav id="home-navbar" :class="{ transparent: hasTransparentBackground }">
    <div class="brand-container" @click.prevent="goToPage('/')">
      <img
        src="/images/logo.png"
        alt=""
        class="brand"
        :class="{ 'tlr--d-none': !hasTransparentBackground }"
      />
      <img
        src="/images/logo-white.png"
        alt=""
        class="brand"
        :class="{ 'tlr--d-none': hasTransparentBackground }"
      />
    </div>
    <div @click="setCollapsed(false)" class="hamburger-container tlr--d-block tlr--d-none-tablet">
      <i class="fas fa-bars"></i>
    </div>
    <div class="nav-links" :class="{collapsed: collapsed}">
      <div @click="setCollapsed(true)"  class="close-button-container tlr--d-flex tlr--d-none-tablet">
        <i class="fas fa-times"></i>
      </div>
      <a href="#" class="nav-link">Teach</a>
      <a href="#" class="nav-link" @click.prevent="showHelpModal()">Help</a>
      <a href="/login" class="nav-link" @click.prevent="goToPage('/login')">Login</a>
      <a href="#" class="nav-link">Success Stories</a>
    </div>
  </nav>
</template>
<script>
export default {
  props: {
  },
  data() {
    return {
      collapsed: true,
      hasTransparentBackground: true
    }
  },
  mounted(){
    this.listenForEvents()
  },
  methods: {
    setCollapsed(val) {
      this.collapsed = val
    },
    showHelpModal() {
      this.$nuxt.$emit('set-help-modal-state', true)
    },
    listenForEvents(){
      this.$nuxt.$on('set-home-navbar-transparent', (val) => {
        this.hasTransparentBackground = val
      })
    },
    goToPage(path){
      event.preventDefault()
      this.$nuxt.$router.push(path)
    }
  }
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#home-navbar {
  --background-color: #{$primaryColor-dark};
  --text-color: white;
  box-shadow: 0px 2px 10px rgba($darkBorderGray, 0.4);
  position: fixed;
  z-index: 10;
  top: 0;
  right: 0;
  left: 0;

  &.transparent {
    --background-color: transparent;
    box-shadow: none;
  }

  background-color: var(--background-color);
  transition: background-color 0.5s ease;
  color: var(--text-color);
  padding: 0 var(--body-padding);
  height: var(--home-navbar-height);
  display: flex;
  align-items: center;
  justify-content: space-between;

  .hamburger-container {
    cursor: pointer;
    padding: 8px;
    font-size: 1.3em;
  }

  .brand-container {
    margin-right: 16px;
    img.brand {
      height: 20px;
      object-fit: contain;
    }
  }

  .nav-links {
    --sidebar-width: 180px;
    display: flex;
    flex-direction: column;
    background: $primaryColor-dark;
    position: fixed;
    width: var(--sidebar-width);
    left: calc(100% - var(--sidebar-width));
    top: 0;
    bottom: 0;
    padding: 16px;
    box-shadow: -1px 1px 7px 0px rgba(#04192d, 0.25);
    transition: left 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    @media only screen and (min-width: 768px) {
      background: transparent;
      position: initial;
      align-items: center;
      flex-direction: row;
      box-shadow: unset;
      width: unset ;
    }

    &.collapsed {
      left: 100%;
    }
    .close-button-container {
      width: 100%;
      font-size: 1.3em;
      padding: 8px;
      justify-content: flex-end;
    }
    .nav-link {
      text-decoration: none;
      color: var(--text-color);
      margin-right: 24px;
      margin-bottom: 8px;
      &:last-child {
        margin-bottom: 0;
      }
      @media only screen and (min-width: 768px) {
        margin-bottom: 0;

        &:last-child {
          margin-right: 0;
        }
      }
    }
  }
}
</style>