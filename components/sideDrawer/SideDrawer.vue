<template>
  <nav class="mb-navbar" :class="{opened: show}">
    <ul class="mb-navbar__items" @click="$emit('sideNavClose')">
      <li v-for="item in mobileNav" :key="item.route" class="mb-navbar__item">
        <nuxt-link class="nav__link" :to="`/${item.route}`">{{item.link}}</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      mobileNav: [
        { route: "about-me", link: "About" },
        { route: "skills", link: "Skills" },
        { route: "my-work", link: "Work" },
        { route: "cv", link: "CV" }
      ]
    };
  },
  props: {
    show: {
      type: Boolean
    }
  }
};
</script>

<style lang="scss">
.mb-navbar {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  z-index: 99;
  background: var(--main-darker);
  display: flex;
  justify-content: center;
  align-items: center;
  &.opened {
    animation: fadeIn2 0.2s ease-in forwards;
  }

  @include medium {
    display: none;
  }
  &__items {
    margin: 0;
    padding: 0;
    list-style: none;
    opacity: 0;
    animation: fadeIn 0.2s 0.25s ease forwards;
    .mb-navbar__item {
      .nav__link {
        display: inline-block;
        padding: 1rem;
        font-size: 3rem;
        font-family: var(--font-ultra-bold);

        color: var(--main-light);
        transition-duration: 0.3s;
        &:hover,
        &.nuxt-link-active {
          color: var(--nav-active-color);
        }
      }
    }
  }
}
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 0.5;
  }
  100% {
    opacity: 1;
  }
}
@keyframes fadeIn2 {
  0% {
    transform: translateX(-100%);
  }
  33% {
    transform: translateX(-66%);
  }
  66% {
    transform: translateX(-33%);
  }
  100% {
    transform: translateX(0);
  }
}
</style>