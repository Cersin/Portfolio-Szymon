<template>
  <nav>
    <a href="#home">HOME</a>
    <a href="#about">O MNIE</a>
    <a href="#">PORTFOLIO</a>
    <a href="#">OFERTA</a>
    <a href="#">KONTAKT</a>
  </nav>
</template>

<script>
export default {
  name: "TheNavigation"
}
</script>

<style scoped lang="scss">
  nav {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    justify-content: right;
    margin-top: $margin-small;
    z-index: 99999;

    @include respond(tablets) {
      display: flex;
    }

    > * {
      margin-right: clamp(2rem, 5vw, 8rem);
    }

    a {
      font-size: clamp(1rem, 1.5vw, 1.6rem);
      text-decoration: none;
      color: $color-black;
      transition: .3s;

      &:hover {
        color: $color-blue;
      }
    }
  }
</style>
