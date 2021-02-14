<template>
  <button class="generic-button" :class="classes">
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
    }
  },
  computed: {
    classes(){
      return {
        'no-border': this.noBorder,
        gray: this.gray
      }
    }
  }
}
</script>

<style lang="scss">
@import '~assets/styles/variables';
.generic-button{
  background: $offWhite;
  border: 1px solid $borderGray;
  border-radius: 5px;
  outline: none;
  padding-right: 12px;
  padding-left: 12px;
  height: 30px;
  white-space: nowrap;
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
}
</style>