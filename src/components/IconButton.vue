<template>
  <button type="button" class="icon-btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'icon-button',
  components: {},
};
</script>
<style lang="scss" scoped>
button.icon-btn {
  border: 0;
  outline: 0;
  width: 48px;
  height: 48px;
  border-radius: 48px;
  background-color: $grey10;
  font-size: 20px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}
</style>
