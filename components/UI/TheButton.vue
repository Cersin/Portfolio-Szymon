<template>
  <button v-on="$listeners">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "TheButton"
}
</script>

<style scoped lang="scss">
button {
  background: linear-gradient(to left, $color-linear-1, $color-linear-2, $color-linear-3);
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
  width: fit-content;
  text-transform: uppercase;
  font-weight: 700;
  color: $color-white;
  padding: 1.5rem;
  border-radius: 3rem;
  border: none;
  cursor: pointer;
  font-size: clamp(1rem, 2vw, 2rem);

  &:hover, &:active {
    opacity: .7;
  }
}
</style>
