<template>
  <transition name="navigation-mobile">
    <nav v-show="show">
      <a @click="$emit('close')" href="#">HOME</a>
      <a @click="$emit('close')" href="#">O MNIE</a>
      <a @click="$emit('close')" href="#">PORTFOLIO</a>
      <a @click="$emit('close')" href="#">OFERTA</a>
      <a @click="$emit('close')" href="#">KONTAKT</a>
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
    display: none;
    flex-direction: column;
    position: fixed;
    height: 100%;
    width: 100%;
    justify-content: space-evenly;
    align-items: center;

    @include respond(tablets) {
      display: flex;
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
