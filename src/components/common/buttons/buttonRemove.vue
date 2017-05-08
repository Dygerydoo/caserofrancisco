<template>
  <span class="tnl-Button-remove" :class="{ 'active': isActive }"></span>
</template>

<script>
export default {
  name: 'button-remove',
  data() {
    return {
      isActive: false,
    };
  }
}
</script>

<style lang="scss" scoped>
@import 'assets/stylesheets/foundation/config';
@import 'assets/stylesheets/foundation/helpers';

.tnl-Button-remove {
  @include ripples;
  display: block;
  z-index: 2;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background: $color-error url('/app/assets/images/icons/trash_white.svg') no-repeat center;
  background-size: 45%;
  box-shadow: $box-shadow-default;
}
</style>
