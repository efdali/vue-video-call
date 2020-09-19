<template>
  <button :class="[{ primary, full }, 'body-regular']">
    <slot></slot>
  </button>
</template>
<script>
export default {
  name: 'Button',
  props: {
    primary: {
      type: Boolean,
      default: false,
    },
    full: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
<style lang="scss" scoped>
button {
  width: 236px;
  height: 48px;
  border: 1px solid $primary;
  background-color: transparent;
  color: $primary;
  border-radius: 8px;
  transition: all 0.2s;
  &.primary {
    background-color: $primary;
    color: $white;
  }
  &.full {
    width: 100%;
  }

  &:hover {
    background-color: $primary;
    color: $white;
  }
}
</style>
