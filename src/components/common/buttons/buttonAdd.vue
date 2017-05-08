<template>
    <div class="tnl-ClickableElement-full" href="#">
        <span class="tnl-Button-add active" :class="{ 'active': isActive }"></span>
    </div>
</template>

<script>
export default {
  name: 'button-add',
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

.tnl-Button-add {
  display: block;
  position: absolute;
  top: 50%;
  right: 10px;
  z-index: 2;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  margin-left: .6em;
  background: $color-tertiary;
  box-shadow: $box-shadow-default;
  transform: translateY(-50%);

  &::before {
    content: '+';
    position: absolute;
    top: 8px;
    left: 10px;
    width: 12px;
    height: 16px;
    color: $white;
    font-size: $font-size-l;
    line-height: 18px;
  }

  &::after {
    content: '';
    transform: scale(0);
    transition: transform 500ms cubic-bezier(.85, .1, .29, .94);;
  }

  .tnl-Cell-floating.active & {
    &.active  {
      background: $color-success;

      &::before {
        content: '';
      }

      &::after {
        content: '';
        position: absolute;
        top: 1px;
        left: 1px;
        width: 30px;
        height: 30px;
        background: url('/app/assets/images/icons/check_mark_white.svg') no-repeat center center;
        background-size: cover;
        font-size: $font-size-l;
        line-height: 18px;
        transform: scale(1);
      }
    }
  }
}
</style>
