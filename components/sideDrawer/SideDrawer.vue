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
  width: 70vw;
  max-width: 400px;
  z-index: 99;
  background: var(--main-darker);
  display: flex;
  justify-content: center;
  align-items: center;
  transition: transform 0.25s ease-in-out;
  transform: translateX(-100%);
  &.opened {
    transform: translateX(0);
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
</style>