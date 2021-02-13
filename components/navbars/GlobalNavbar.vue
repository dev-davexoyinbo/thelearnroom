<template>
  <nav id="global-navbar">
    <div class="brand-container">
      <img src="/images/logo.png" alt="" class="brand" />
    </div>
    <div
      @click="setCollapsed(false)"
      class="hamburger-container tlr--d-block tlr--d-none-tablet"
    >
      <i class="fas fa-bars"></i>
    </div>
    <div class="nav-links" :class="{ collapsed: collapsed }">
      <div
        @click="setCollapsed(true)"
        class="close-button-container tlr--d-flex tlr--d-none-tablet"
      >
        <i class="fas fa-times"></i>
      </div>
      <a href="#" class="nav-link"
        ><i class="fas fa-search"></i> Find a class</a
      >
      <a href="#" class="nav-link"
        ><i class="fas fa-chalkboard-teacher"></i> Teach</a
      >
      <a href="#" class="nav-link" @click.prevent="showHelpModal()"
        ><i class="far fa-question-circle"></i> Help</a
      >
      <a href="#" class="nav-link"><i class="fas fa-sign-in-alt"></i> Login</a>
      <button href="#" class="nav-link btn">Join for free</button>
    </div>
  </nav>
</template>
<script>
export default {
  props: {},
  data() {
    return {
      collapsed: true,
      hasTransparentBackground: true,
    };
  },
  methods: {
    setCollapsed(val) {
      this.collapsed = val;
    },
    showHelpModal() {
      event.preventDefault()
      this.$nuxt.$emit('set-help-modal-state', true)
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#global-navbar {
  --background-color: white;
  --text-color: #{$textColor};
  box-shadow: 0px 3px 10px rgba($darkColor, 0.18);
  position: sticky;
  z-index: 10;
  top: 0;
  right: 0;
  left: 0;

  background-color: var(--background-color);
  transition: background-color 0.5s ease;
  color: var(--text-color);
  padding: 0 var(--body-padding);
  height: var(--global-navbar-height);
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
    background: white;
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
      width: unset;
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
      margin-right: 20px;
      margin-bottom: 8px;
      &:last-child {
        margin-bottom: 0;
      }

      &.btn {
        width: 100%;
		padding: 12px 16px;
		background: $primaryColor;
		color: white;
		border: none;
		outline: none;
		border-radius: 5px;
		&:active {
			outline: none;
		}
      }
      @media only screen and (min-width: 768px) {
        margin-bottom: 0;

        &.btn {
          width: unset;
        }

        &:last-child {
          margin-right: 0;
        }
      }
    }
  }
}
</style>