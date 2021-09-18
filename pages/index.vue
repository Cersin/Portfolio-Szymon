<template>
  <div class="site">
    <Home></Home>
    <About></About>
  </div>
</template>

<style scoped>

</style>
<script>
import Home from "../components/pages/Home";
import About from "../components/pages/About";
export default {
  components: {About, Home},
  data() {
    return {
    }
  },
  mounted() {
    this.setVh();
  },
  methods: {
    setVh() {
      let vh = window.innerHeight * 0.01
      document.documentElement.style.setProperty('--vh', `${vh}px`);
    }
  }
}
</script>
