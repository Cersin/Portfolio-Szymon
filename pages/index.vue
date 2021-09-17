<template>
  <div class="site">
    <Home></Home>
    <About></About>
  </div>
</template>

<style scoped>
.site {
}
</style>
<script>
import Home from "../components/pages/Home";
import About from "../components/pages/About";
export default {
  components: {About, Home}
}
</script>
