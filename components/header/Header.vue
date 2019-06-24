<template>
  <div class="header">
    <header>
      <nuxt-link class="logo__wrapper" :class="{visible: !drawerState}" to="/">
        <!-- <img class="logo" src="/images/nuxt.png" alt> -->
        <svg
          class="logo"
          xmlns:dc="http://purl.org/dc/elements/1.1/"
          xmlns:cc="http://creativecommons.org/ns#"
          xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
          xmlns:svg="http://www.w3.org/2000/svg"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
          xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
          id="a6ee8617-cc99-4eb9-a93b-e1a7e83c9724"
          data-name="Layer 1"
          width="652"
          height="276"
          viewBox="0 0 652 275.99999"
          version="1.1"
          sodipodi:docname="logo.svg"
          inkscape:version="0.92.4 (5da689c313, 2019-01-14)"
        >
          <defs id="defs109"></defs>
          <polygon
            points="719.6,311.194 749.6,281.294 878,409.294 749.6,537.294 719.6,507.394 818,409.294 "
            id="polygon6"
            style="opacity:0.2"
            transform="translate(-226,-261.294)"
          ></polygon>
          <path
            d="m 212.6,154.99962 h 40 v -40 h -40 z m 200.8,-40 h -40 v 40 h 40 z m -120.4,40 h 40 v -40 h -40 z"
            id="path8"
            inkscape:connector-curvature="0"
            style="opacity:0.2"
          ></path>
          <polygon
            points="384.3,310.194 354.3,280.294 226,408.294 354.4,536.294 384.4,506.394 285.9,408.294 "
            id="polygon10"
            style="opacity:0.2"
            transform="translate(-226,-261.294)"
          ></polygon>
          <polygon
            points="719.6,488.394 818,390.294 719.6,292.194 749.6,262.294 878,390.294 749.6,518.294 "
            id="polygon44"
            style="fill:var(--main-accent)"
            transform="translate(-226,-261.294)"
          ></polygon>
          <path
            d="m 212.6,135.99962 h 40 v -40 h -40 z m 200.8,-40 h -40 v 40 h 40 z m -120.4,40 h 40 v -40 h -40 z"
            id="path70"
            inkscape:connector-curvature="0"
            style="fill:var(--main-accent)"
          ></path>
          <polygon
            points="384.3,291.194 354.3,261.294 226,389.294 354.4,517.294 384.4,487.394 285.9,389.294 "
            id="polygon80"
            style="fill:var(--main-accent)"
            transform="translate(-226,-261.294)"
          ></polygon>
        </svg>
      </nuxt-link>
      <ul class="navbar">
        <li v-for="item in navbar" :key="item.route" class="navbar__item">
          <nuxt-link class="link" :to="`/${item.route}`">{{item.link}}</nuxt-link>
        </li>
      </ul>
      <Hamburger :sideNavState="drawerState" @toggleDrawer="$emit('toggle-drawer')"/>
    </header>
  </div>
</template>

<script>
import Hamburger from "~/components/sideDrawer/Hamburger";
export default {
  components: {
    Hamburger
  },
  data() {
    return {
      navbar: [
        { route: "about-me", link: "About" },
        { route: "skills", link: "Skills" },
        { route: "my-work", link: "Work" },
        { route: "cv", link: "CV" }
      ]
    };
  },
  props: {
    drawerState: {
      type: Boolean
    }
  }
};
</script>

<style scoped lang="scss">
.header {
  background: var(--nav-bg);
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 150;
  header {
    height: 60px;
    // background: #444;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    color: var(--nav-color);
    width: 100%;
    max-width: 1280px;
    margin: 0 auto;
    .logo__wrapper {
      cursor: pointer;
      opacity: 0;
      width: 4rem;
      height: auto;
      display: flex;
      justify-content: flex-start;
      align-items: flex-start;
      &.visible {
        opacity: 1;
        z-index: 10;
      }
      .logo {
        width: 100%;
        height: 100%;
      }
    }
    .navbar {
      margin: 0;
      padding: 0;
      list-style: none;
      display: none;
      @include medium {
        display: flex;
      }
      &__item {
        position: relative;
        text-align: center;
        transition-duration: 0.3s;
        .link {
          position: relative;
          color: var(--nav-color);
          font-size: 1.19rem;
          display: inline-block;
          padding: 1.19rem;
          cursor: pointer;
          transition: color 0.3s ease-in-out;
          &:after {
            content: "";
            background-color: var(--nav-active-color);
            transform: scaleX(0);
            // transform-origin: left;
            position: absolute;
            bottom: 0;
            left: 0;
            height: 3px;
            width: 100%;
            transition: transform 0.3s ease-in-out;
          }
          &:hover,
          &.nuxt-link-active {
            color: var(--nav-active-color);
            &:after {
              transform: scaleX(1);
            }
          }
        }
      }
    }
  }
}
</style>
