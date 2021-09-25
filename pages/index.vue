<template>
  <div class="site">
    <Home class="margin-side-mobile margin-side-desktop margin-side-big"></Home>
    <About class="margin-side-mobile margin-side-desktop margin-side-big"></About>
    <Portfolio class="margin-side-mobile margin-side-desktop margin-side-big"></Portfolio>
    <Offer></Offer>
    <OfferDescribe class="margin-side-mobile margin-side-desktop margin-side-big"></OfferDescribe>
    <Contact class="margin-side-mobile"></Contact>
  </div>
</template>

<style scoped>

</style>
<script>
import Home from "../components/pages/Home";
import About from "../components/pages/About";
import Portfolio from "../components/pages/Portfolio";
import Offer from "../components/pages/Offer";
import OfferDescribe from "../components/pages/Offer-Describe";
import Contact from "../components/pages/Contact";
export default {
  components: {Contact, OfferDescribe, Offer, Portfolio, About, Home},
  mounted() {
    this.setVh();
    window.addEventListener('resize', this.setVh);
  },
  methods: {
    setVh() {
      console.log('chk');
      let vh = window.innerHeight * 0.01
      document.documentElement.style.setProperty('--vh', `${vh}px`);
    }
  }
}
</script>
