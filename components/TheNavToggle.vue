<template>
  <div class="toggle margin-side-mobile">
    <div @click="$emit('toggleNavMobile')" class="toggle-line" :class="{transform: toggleButton}"></div>
  </div>
</template>

<script>
export default {
  name: "TheNavToggle",
  props: {
    toggleButton: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
.toggle {
  display: flex;
  position: fixed;
  margin-top: $margin-small + 2rem;
  z-index: 9999;
  transition: .5s;

  @include respond(tablets) {
    display: none;
  }

  &-line {
    width: 2rem;
    height: .2rem;
    background-color: $color-grey;
    //transform: rotate(45deg);

    &::after, &::before {
      content: '';
      position: absolute;
      width: inherit;
      height: inherit;
      background-color: inherit;
    }

    &::after {
      top: .5rem;
    }

    &::before {
      top: -.5rem;
    }
  }

  .transform {
    transform: rotate(405deg);
    transition: .5s;

    &::after {
      display: none;
    }

    &::before {
      top: 0;
      transform: rotate(90deg);
    }
  }
}

</style>
