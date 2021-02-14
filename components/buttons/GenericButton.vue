<template>
  <button class="generic-button" :class="classes" :style="{'--size-factor': this.sizeFactor}">
    <slot>Generic Button</slot>
  </button>
</template>

<script>
export default {
  props: {
    noBorder : {
      default: false,
    },
    gray : {
      default: false
    },
    primary: {
      default: false
    },
    sizeFactor: {
      default: 1
    },
    primaryDark: {
      default: false
    },
    bgLight: {
      default: false
    },
    textPrimary: {
      default: false
    },
    withShadow: {
      default: false
    }
  },
  computed: {
    classes(){
      return {
        'no-border': this.noBorder,
        gray: this.gray,
        primary: this.primary,
        'primary-dark': this.primaryDark,
        'bg-light' : this.bgLight,
        'text-primary': this.textPrimary,
        'with-shadow': this.withShadow,
      }
    }
  }
}
</script>

<style lang="scss">
@import '~assets/styles/variables';
.generic-button{
  --size-factor: 1;
  background: $offWhite;
  border: 1px solid $borderGray;
  border-radius: calc(var(--size-factor) * 5px);
  outline: none;
  padding-right: calc(var(--size-factor) * 12px);
  padding-left: calc(var(--size-factor) * 12px);
  height: calc(var(--size-factor) * 30px);
  font-size: calc(var(--size-factor) * 1rem);;
  white-space: nowrap;
  cursor: pointer;
  color: #6E6E6E;
  &:active {
    outline: none;
  }

  &.no-border {
    border:none;
  }

  &.gray {
    background: #7A8CA9;
    color: white;
  }

  &.primary {
    background: $primaryColor;
    color: white;
  }

  &.primary-dark {
    background: $primaryColor-dark-2;
    color: white;
  }

  &.bg-light {
    background: white;
  }

  &.text-primary {
    color: $primaryColor;
  }

  &.with-shadow {
    box-shadow: 1px 2px 5px rgba($darkColor, 0.3);
  }
}
</style>