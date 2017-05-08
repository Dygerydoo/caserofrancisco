<template>
  <a v-if="setUrl"
     :href="setUrl"
     :class="chooseProperClass">
    <slot></slot>
  </a>

  <button v-else
          :type="isSubmit ? 'submit' : 'button'"
          :class="chooseRightClass"
          @click="$emit('click')">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'button-base',
  props: {
    setClass: {
      type: String,
    },
    sizeSmall: {
      type: Boolean,
    },
    isSubmit: {
      type: Boolean,
    },
    setUrl: [String, Boolean],
  },
  computed: {
    chooseProperClass: function() {
      if (this.sizeSmall && !this.setClass) {
        return 'tnl-Button-small';
      } else if (this.sizeSmall && this.setClass) {
        return 'tnl-Button-' + this.setClass + 'Small';
      } else if (!this.sizeSmall && this.setClass) {
        return 'tnl-Button-' + this.setClass;
      } else {
        return 'tnl-Button';
      }
    },
  },
}

</script>

<style lang="scss">
@import 'assets/stylesheets/foundation/config';
@import 'assets/stylesheets/foundation/helpers';
@import './buttons';
</style>
