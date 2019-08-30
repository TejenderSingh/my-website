<template>
  <div>
    <Header :drawerState="sideDrawerOpen" @toggle-drawer="sideDrawerOpen = !sideDrawerOpen" />
    <SideDrawer :show="sideDrawerOpen" @sideNavClose="sideDrawerOpen = false" />
    <nuxt />
    <Footer />
  </div>
</template>


<script>
import Header from "~/components/header/Header";
import Footer from "~/components/footer/Footer";
import SideDrawer from "~/components/sideDrawer/SideDrawer";

export default {
  data() {
    return {
      sideDrawerOpen: false,
      width: 0
    };
  },

  mounted() {
    window.addEventListener("resize", this.handleResize);
  },
  destroyed() {
    window.removeEventListener("resize", this.handleResize);
  },
  methods: {
    handleResize() {
      this.width = window.innerWidth;
      if (this.width >= 600) {
        this.sideDrawerOpen = false;
      }
    }
  },

  components: {
    Header,
    SideDrawer,
    Footer
  }
};
</script>



<style>
</style>
