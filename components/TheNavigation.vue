<template>
  <nav>
    <a href="#home">Home</a>
    <a href="#about">O mnie</a>
    <a href="#portfolio">Portfolio</a>
    <a href="#oferta">Oferta</a>
    <a href="#kontakt">Kontakt</a>
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
    transition: all .5s;

    @include respond(tablets) {
      display: flex;
    }

    > * {
      margin-right: clamp(2rem, 5vw, 10rem);
    }

    a {
      font-size: clamp(1rem, 1.5vw, 1.7rem);
      font-weight: 600;
      text-decoration: none;
      color: $color-black;
      transition: .3s;

      &:hover {
        color: $color-blue;
      }
    }
  }
</style>
