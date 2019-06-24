<template>
  <div class="nav-icon" :class="{open:sideNavState}" @click="$emit('toggleDrawer')">
    <span></span>
    <span></span>
    <span></span>
  </div>
</template>

<script>
export default {
  props: {
    sideNavState: {
      type: Boolean
    }
  }
};
</script>

<style scoped lang="scss">
.nav-icon {
  position: relative;
  z-index: 999;
  width: 36px;
  height: 27px;
  transform: rotate(0deg);
  transition: 0.5s ease-in-out;
  cursor: pointer;
  &.open span {
    background: var(--main-accent);
  }
  &.open span:nth-child(1) {
    top: 11px;
    transform: rotate(135deg);
  }
  &.open span:nth-child(2) {
    opacity: 0;
    right: -60px;
  }
  &.open span:nth-child(3) {
    top: 11px;
    transform: rotate(-135deg);
  }
  span {
    display: block;
    position: absolute;
    height: 5px;
    width: 100%;
    background: var(--main-light);
    border-radius: 5px;
    opacity: 1;
    left: 0;
    transform: rotate(0deg);
    transition: 0.25s ease-in-out;
    &:nth-child(1) {
      top: 0px;
    }
    &:nth-child(2) {
      top: 11px;
    }
    &:nth-child(3) {
      top: 22px;
    }
  }
  @include medium {
    display: none;
  }
}
</style>