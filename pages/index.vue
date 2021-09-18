<template>
  <div class="site">
    <Home></Home>
    <About></About>
    <Portfolio></Portfolio>
  </div>
</template>

<style scoped>

</style>
<script>
import Home from "../components/pages/Home";
import About from "../components/pages/About";
import Portfolio from "../components/pages/Portfolio";
export default {
  components: {Portfolio, About, Home},
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
