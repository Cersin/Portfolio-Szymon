<template>
  <transition name="navigation-mobile">
    <nav v-show="show">
      <a @click="$emit('close')" href="#home">Home</a>
      <a @click="$emit('close')" href="#about">O mnie</a>
      <a @click="$emit('close')" href="#portfolio">Portfolio</a>
      <a @click="$emit('close')" href="#oferta">Oferta</a>
      <a @click="$emit('close')" href="#kontakt">Kontakt</a>
    </nav>
  </transition>
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
    display: flex;
    flex-direction: column;
    position: fixed;
    height: 100%;
    width: 100%;
    justify-content: space-evenly;
    align-items: center;
    z-index: 999;
    background-color: rgba($color-white, .7);
    font-weight: 600;

    @include respond(tablets) {
      display: none;
    }

    a {
      font-size: 3rem;
      text-decoration: none;
      color: $color-black;
      transition: .3s;

      &:hover {
        color: $color-blue;
      }
    }
  }

  .navigation-mobile {
    &-enter-active, &-leave-active {
      transition: all .5s ease-in-out;
    }

    &-enter, &-leave-to {
      transform: translateX(-100vw);
    }
  }
</style>
