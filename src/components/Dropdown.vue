<template>
  <div class="dropdown-container" @keypress.down="konsol">
    <div class="overview" v-show="showMenu" @click="showMenu = false"></div>
    <div
      class="dropdown"
      @click="showMenu = !showMenu"
      @keypress.enter="showMenu = !showMenu"
      tabindex="0"
    >
      <div class="input" @keypress.down="konsol">
        <CustomText br>{{ selected }}</CustomText>
        <ArrowDown />
      </div>
      <ul
        :class="['dropdown-items', { show: showMenu }]"
        @keypress.down="konsol"
      >
        <li v-for="item in list" :key="item.key" @click="selected = item.value">
          <CustomText br>{{ item.value }}</CustomText>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import CustomText from '@/components/CustomText.vue';
import ArrowDown from '@/icons/arrow-down.svg';
export default {
  name: 'Dropdown',
  components: { CustomText, ArrowDown },
  props: {
    list: Array,
  },
  data() {
    return {
      selected: this.list[0].value,
      showMenu: false,
    };
  },
};
</script>
<style lang="scss" scoped>
.dropdown-container {
  position: relative;
}
.overview {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
}
.dropdown {
  width: 236px;
  height: 48px;
  border: 1px solid $grey40;
  padding: 15px 16px;
  border-radius: 8px;
  position: relative;
  cursor: pointer;

  .input {
    height: 100%;
    font-size: 18px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    span {
      font-size: 15px;
      -webkit-line-clamp: 1;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;

      &::selection {
        background-color: transparent;
      }
    }
  }

  &-items {
    position: absolute;
    top: 90%;
    left: -1px;
    right: 0;
    width: calc(100% + 2px);
    border: 1px solid $grey40;
    border-top: 0;
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
    transition: all 0.2s;
    background-color: $white;
    z-index: 3;
    transform: scaleY(0);
    transform-origin: 0 0;

    &.show {
      box-shadow: 0 5px 5px $grey40;
      transform: scaleY(1);
    }

    li {
      padding: 10px 8px;
      &.selected {
        background-color: $grey10;
      }
      &:hover {
        background-color: $grey10;
      }
    }
  }
}
</style>
