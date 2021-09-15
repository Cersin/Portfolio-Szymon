<template>
  <nav>
    <a href="#">HOME</a>
    <a href="#">O MNIE</a>
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
    display: flex;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    justify-content: right;
    margin-top: $margin-small;
    @include respond(tablets) {
      display: none;
    }

    > * {
      margin-right: clamp(2rem, 5vw, 8rem);
    }

    a {
      font-size: 1.8rem;
      text-decoration: none;
      color: $color-black;
      transition: .3s;

      &:hover {
        color: $color-blue;
      }
    }

    button {
      margin-right: 3rem;
    }
  }
</style>
