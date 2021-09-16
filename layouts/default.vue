<template>
  <div>
    <TheNavigation></TheNavigation>
    <TheNavToggle @toggleNavMobile="displayMobileNav = !displayMobileNav" :toggleButton="displayMobileNav"></TheNavToggle>
    <TheNavigationMobile :show="displayMobileNav" @close="displayMobileNav = false"></TheNavigationMobile>
    <Nuxt class="margin-side-mobile margin-side-desktop" />
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
      displayMobileNav: false
    }
  }
}
</script>
