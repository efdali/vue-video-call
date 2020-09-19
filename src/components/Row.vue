<template>
  <div class="row" :style="gapStyle">
    <CustomText br>{{ text }}</CustomText>
    <slot></slot>
  </div>
</template>
<script>
import CustomText from '@/components/CustomText.vue';
export default {
  name: 'Row',
  components: { CustomText },
  props: {
    text: String,
    containerGap: {
      type: String,
      default: '8px',
    },
    gapOrientation: {
      type: String,
      default: 'vertical',
    },
  },
  computed: {
    gapStyle: function() {
      let style = {};
      if (this.gapOrientation === 'vertical') {
        style.marginBottom = this.containerGap;
      } else {
        style.marginRight = this.containerGap;
      }
      return style;
    },
  },
};
</script>
<style scoped>
.row {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
