<template>
  <div class="toggle">
    <div @click="$emit('toggleNavMobile')" class="toggle-line"></div>
  </div>
</template>

<script>
export default {
  name: "TheNavToggle"
}
</script>

<style scoped lang="scss">
.toggle {
  display: flex;
  position: fixed;
  margin-top: $margin-small + 2rem;
  margin-left: $margin-small + 1rem;
  z-index: 9999;

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
      //display: none;
    }

    &::before {
      top: -.5rem;
      //transform: rotate(90deg);
    }
  }
}

</style>
