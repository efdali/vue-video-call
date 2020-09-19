<template>
  <span :is="tag" :class="classname"><slot></slot></span>
</template>
<script>
export default {
  name: 'CustomText',
  props: {
    tag: {
      type: String,
      default: 'span',
    },
    sr: Boolean,
    tb: Boolean,
    br: Boolean,
    bb: Boolean,
  },
  computed: {
    classname: function() {
      return {
        'small-regular': this.sr,
        'title-bold': this.tb,
        'body-regular': this.br,
        'body-bold': this.bb,
      };
    },
  },
};
</script>
