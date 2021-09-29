<template>
  <div>
    <Home id="home" class="margin-side-mobile margin-side-desktop margin-side-big"></Home>
    <About id="about" class="margin-side-mobile margin-side-desktop margin-side-big"></About>
    <Portfolio id="portfolio" class="margin-side-mobile margin-side-desktop margin-side-big"></Portfolio>
    <Offer id="oferta"></Offer>
    <OfferDescribe id="offerDescribe" class="margin-side-mobile margin-side-desktop margin-side-big"></OfferDescribe>
    <Contact id="kontakt" class="margin-side-mobile"></Contact>
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
  data() {
    return {
      list: ['about']
    }
  },
  mounted() {
    this.setVh();
    this.addActive();
    window.addEventListener('resize', this.setVh);
    window.addEventListener('scroll', this.addActive);
  },
  methods: {
    setVh() {
      let vh = window.innerHeight * 0.01
      document.documentElement.style.setProperty('--vh', `${vh}px`);
    },
    addActive() {
      this.list.forEach((el) => {
        const element = document.getElementById(el);
        const top = element.offsetTop;
        const height = element.offsetHeight;

        if (window.scrollY >= top - 300 && window.scrollY < top + height - 300) {
          element.classList.add('animate');
          if (element.id === 'about') {
            const technologies = document.getElementsByClassName('about_technologies-svg');
            for (let i = 0; i < technologies.length; i++) {
              setTimeout(() => {
                technologies[i].classList.add('animate');
              }, i * 500);
            }
          }
        }
      })


    }
  }
}
</script>
