<template>
  <div>
    <TheNavigation></TheNavigation>
    <TheNavToggle @toggleNavMobile="displayMobileNav = !displayMobileNav"></TheNavToggle>
    <TheNavigationMobile :show="displayMobileNav"></TheNavigationMobile>
    <Nuxt />
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
