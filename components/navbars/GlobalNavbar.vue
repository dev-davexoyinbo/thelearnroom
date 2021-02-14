<template>
  <nav id="global-navbar">
    <div class="brand-container" @click.prevent="goToPage('/')">
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
      <a
        href="/students/find-class"
        class="nav-link"
        @click="goToPage('/students/find-class')"
        ><i class="fas fa-search"></i> Find a class</a
      >
      <a href="#" class="nav-link"
        ><i class="fas fa-chalkboard-teacher"></i> Teach</a
      >
      <a href="#" class="nav-link" @click.prevent="showHelpModal()"
        ><i class="far fa-question-circle"></i> Help</a
      >
      <a href="/login" class="nav-link" @click="goToPage('/login')"
        ><i class="fas fa-sign-in-alt"></i> Login</a
      >
      <button href="#" class="nav-link btn" v-if="!loggedIn">
        Join for free
      </button>
      <button
        href="#"
        class="nav-link btn profile"
        v-if="loggedIn"
        @click="showProfileDropdownMethod()"
      >
        Profile
        <div
          ref="profileDropdown"
          class="dropdown"
          :class="{ 'show-profile-dropdown': showProfileDropdown }"
        >
          <div ref="dropdownList" class="dropdown-list">
            <div class="dropdown-list-item">
              <i class="far fa-comments"></i>
              <div>Conversation</div>
            </div>
            <div class="dropdown-list-item">
              <i class="far fa-heart"></i>
              <div>Favorites</div>
            </div>

            <div class="divider"></div>

            <div class="dropdown-list-item">
              <i class="far fa-calendar-alt"></i>
              <div>Schedule</div>
            </div>

            <div class="dropdown-list-item">
              <i class="far fa-money-bill-alt"></i>
              <div>Purchases</div>
            </div>
            <div class="dropdown-list-item">
              <i class="fas fa-chalkboard-teacher"></i>
              <div>Teach</div>
            </div>

            <div class="divider"></div>

            <div class="dropdown-list-item">
              <i class="fas fa-envelope-open-text"></i>
              <div>Invite Teacher</div>
            </div>
            <div class="dropdown-list-item">
              <i class="fas fa-envelope-open-text"></i>
              <div>Invite Parent</div>
            </div>

            <div class="dropdown-list-item">
              <i class="fas fa-gift"></i>
              <div>Gift a card</div>
            </div>

            <div class="divider"></div>
            <div class="dropdown-list-item">
              <i class="fas fa-cogs"></i>
              <div>Profile & Settings</div>
            </div>
            <div class="dropdown-list-item">
              <i class="far fa-comments"></i>
              <div>Help</div>
            </div>
            <div class="dropdown-list-item">
              <i class="fas fa-sign-out-alt"></i>
              <div>Logout</div>
            </div>
          </div>
        </div>
      </button>
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
      isShowingProfileDropdown: false,
    };
  },
  mounted() {
    this.$nextTick(() => {
      document.addEventListener("click", this.profileDropdownListener);
      document.addEventListener("touch", this.profileDropdownListener);
    });
  },
  beforeDestroy() {
    document.removeEventListener("click", this.profileDropdownListener);
    document.removeEventListener("touch", this.profileDropdownListener);
  },
  methods: {
    profileDropdownListener(event) {
      const profileDropdown = this.$refs.profileDropdown;
      const dropdownList = this.$refs.dropdownList;

      if (event.path.some((el) => el == profileDropdown)) {
        if (!event.path.some((el) => el == dropdownList)) {
          event.preventDefault();
          this.isShowingProfileDropdown = false;
        }
      }
    },
    setCollapsed(val) {
      this.collapsed = val;
    },
    showHelpModal() {
      event.preventDefault();
      this.$nuxt.$emit("set-help-modal-state", true);
    },
    goToPage(path) {
      event.preventDefault();
      this.$nuxt.$router.push(path);
    },
    showProfileDropdownMethod() {
      if (event.target != event.currentTarget) return;
      this.isShowingProfileDropdown = !this.isShowingProfileDropdown;
    },
  },
  computed: {
    loggedIn() {
      return true;
    },
    showProfileDropdown() {
      // return !this.collapsed && this.isShowingProfileDropdown
      return this.isShowingProfileDropdown;
    },
  },
  watch: {
    $route(to, from) {
      this.setCollapsed(true);
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#global-navbar {
  --background-color: white;
  --text-color: #{$textColor};
  box-shadow: 0px 3px 10px rgba($darkColor, 0.08);
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
      cursor: pointer;
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

        &.profile {
          --arrow-size: 10px;
          position: relative;
          z-index: 1;
          .dropdown {
            --dropdown-padding: 16px;
            position: absolute;
            
            color: #3c3c3c;
            top: calc(100% + var(--arrow-size));
            bottom: unset;
            right: 0;
            border-radius: 5px;
            box-shadow: -2px 2px 10px rgba($darkColor, 0.28);
            width: 200px;
            text-align: left;
            display: none;

            

            

            &::after {
              content: "";
              position: absolute;
              right: 8px;
              bottom: 100%;
              border-top: none;
              border-right: var(--arrow-size) solid transparent;
              border-left: var(--arrow-size) solid transparent;
              border-bottom: var(--arrow-size) solid #fbfbfb;
              z-index: 2;
            }

            &::before {
              content: "";
              position: fixed;
              top: 0;
              right: 0;
              bottom: 0;
              left: 0;
              background: rgba($darkColor, 0.1);
              z-index: -1;
            }

            //for small screen height
            @media only screen and (max-height: 660px) and (max-width: 767.98px){
              position: fixed;
              z-index: 1;
              bottom: 16px;
              top: unset;
              right: 16px;

              &::after {
                display: none;
              }
            }

            &.show-profile-dropdown {
              display: block;
            }
            .dropdown-list {
              background: #fbfbfb;
              font-size: 0.9rem;
              border-radius: 5px;
              border-top: 5px solid $borderGray;
              padding: 8px 0;

              .divider {
                height: 1px;
                background: rgba($borderGray, 0.6);
              }

              .dropdown-list-item {
                height: 35px;
                display: grid;
                grid-template-columns: 16px 1fr;
                gap: 8px;
                align-items: center;
                padding: 0 var(--dropdown-padding);
                cursor: pointer;
              }
            }
          }
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