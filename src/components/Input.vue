<template>
  <div class="input-container">
    <User />
    <input class="body-regular" type="text" v-model="value" />
  </div>
</template>
<script>
import User from '@/icons/user.svg';
export default {
  name: 'Input',
  components: {
    User,
  },
  data() {
    return {
      value: 'Adem İlter',
    };
  },
};
</script>
<style lang="scss" scoped>
.input-container {
  border: 1px solid $grey40;
  height: 48px;
  border-radius: 8px;
  font-size: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 16px 12px;
  color: $primary;

  input {
    flex: 1;
    color: $grey90;
    margin-left: 6px;
  }
}
</style>
