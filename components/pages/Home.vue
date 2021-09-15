<template>
  <section class="home">
    <div class="home_description">
      <p class="home_description-hi">Cześć, nazywam się</p>
      <p class="home_description-name">SZYMON WÓJCIK.</p>
      <p class="home_description-developer">Jestem <span>Front-end Developerem</span>.</p>
    </div>
    <div class="home_photo">
    </div>
  </section>
</template>

<script>
export default {
  name: "Home"
}
</script>

<style scoped lang="scss">
.home {
  display: flex;
  flex-direction: column;
  padding-top: 5rem;
  height: 100vh;
  justify-content: space-evenly;
  margin: 0 $margin-small + 1rem;

  &_description {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 50%;

    :not(:last-child) {
      margin-bottom: 3px;
    }

    &-hi {
      font-size: clamp(1rem, 3.5vw, 2rem);
    }

    &-name {
      font-size: clamp(2rem, 6vw, 4rem);
    }

    &-developer {
      font-size: clamp(1.5rem, 5vw, 3rem);

      span {
        color: $color-blue;
        font-weight: bold;
      }
    }
  }

  &_photo {
    height: 50%;
    background-color: blue;
  }
}

</style>
