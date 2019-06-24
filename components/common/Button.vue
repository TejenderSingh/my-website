<template>
  <div>
    <nuxt-link
      class="button"
      :to="targetPage"
      :style="{background: btnBgColor, color:btnColor}"
    >{{btnName}}</nuxt-link>
  </div>
</template>

<script>
export default {
  props: {
    btnName: {
      type: String
    },
    btnBgColor: {
      type: String
    },
    btnColor: {
      type: String
    },
    targetPage: {
      type: String
    }
  }
};
</script>

<style lang="scss">
.button {
  display: inline-block;
  padding: 0.8em 1.5em;
  border-radius: 0.2em;
  font-size: 1rem;
  font-family: var(--font-bold);
  letter-spacing: 0.1rem;
  position: relative;
  overflow: hidden;
  z-index: 1;
  @include medium {
    font-size: 1.1rem;
  }
  &:before {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0%;
    height: 100%;
    border-radius: 0.2em;
    background: var(--main-light);
    transition: all 0.25s ease-in-out;
    z-index: -1;
  }
  &:hover {
    &:before {
      width: 110%;
    }
  }
}
</style>