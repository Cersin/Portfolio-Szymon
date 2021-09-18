<template>
  <a :href="goto" class="arrow" :class="direction"></a>
</template>

<script>
export default {
  name: "TheArrow",
  props: {
    direction: {
      type: String,
      default: "down"
    },
    goto: {
      type: String,
      default: "#"
    }
  }
}
</script>

<style scoped lang="scss">
.arrow {
  border: solid $color-blue;
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 10px;
  justify-self: center;
  grid-area: arrow;
  align-self: center;

  @include respond(tablets) {
    padding: 14px;
  }
}

.up {
  transform: rotate(-135deg);
  -webkit-transform: rotate(-135deg);
}

.down {
  transform: rotate(45deg);
  -webkit-transform: rotate(45deg);
}
</style>
