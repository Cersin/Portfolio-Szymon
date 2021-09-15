<template>
    <nav v-show="show">
      <h1>ELo</h1>
    </nav>
</template>

<script>
export default {
  name: "TheNavigationMobile",
  props: {
    show: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
  nav {
    position: fixed;
    height: 100%;
    width: 100%;
  }
</style>
