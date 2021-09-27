<template>
  <div>
    <TheNavigation :class=" { 'nav-visible': scrolled }"></TheNavigation>
    <TheNavToggle @toggleNavMobile="displayMobileNav = !displayMobileNav"
                  :toggleButton="displayMobileNav"></TheNavToggle>
    <TheNavigationMobile :show="displayMobileNav" @close="displayMobileNav = false"></TheNavigationMobile>
    <Nuxt :class=" { active: displayMobileNav } "/>
  </div>

</template>
<script>
import TheNavigation from "../components/TheNavigation";
import TheNavToggle from "../components/TheNavToggle";
import TheNavigationMobile from "../components/TheNavigationMobile";

export default {
  components: {TheNavigationMobile, TheNavToggle, TheNavigation},
  data() {
    return {
      displayMobileNav: false,
      scrolled: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.checkNav);
  },
  watch: {
    displayMobileNav(state) {
      let x = window.scrollX;
      let y = window.scrollY;
      if (state) {
        window.onscroll = () => {
          window.scrollTo(x, y);
        };
      } else window.onscroll = () => {}
    }
  },
  methods: {
    checkNav() {
      if (window.scrollY > 0) this.scrolled = true
      else this.scrolled = false
    }
  }
}
</script>

<style lang="scss">
.active {
  filter: blur(8px);
}

.nav-visible {
  background-color: $color-white;
  margin: 0 !important;
  padding: 0 !important;
}
</style>
