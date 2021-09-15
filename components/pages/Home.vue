<template>
  <section class="home margin-side-desktop margin-side-mobile">
    <div class="home_description">
      <p class="home_description-hi">Cześć, nazywam się</p>
      <p class="home_description-name">SZYMON WÓJCIK.</p>
      <p class="home_description-developer">Jestem <span>Front-end Developerem</span>.</p>
    </div>
    <div class="home_photo">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
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

  &_description {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 50%;

    :not(:last-child) {
      margin-bottom: 3px;
    }

    &-hi {
      font-size: clamp(1.5rem, 1.5vw, 3rem);
    }

    &-name {
      font-size: clamp(3rem, 6vw, 7rem);
      //font-size: 70px;
    }

    &-developer {
      font-size: clamp(2rem, 2vw, 4rem);
      //font-size: 35px;

      span {
        color: $color-blue;
        font-weight: bold;
      }
    }
  }

  &_photo {
    position: relative;
    height: 50%;
    width: 100%;

    > * {
      display: flex;
      position: absolute;
      height: 100%;
      width: 100%;
      justify-content: center;
      background-image: url("static/me.png");
      background-position: center;
      background-size: cover;
    }

    :first-child {
      clip-path: polygon(0% 0%, 0% 100%, 15% 100%, 15% 0%);
    }

    :nth-child(2) {
      clip-path: polygon(20% 0%, 20% 100%, 35% 100%, 35% 0%);
    }

    :nth-child(3) {
      clip-path: polygon(40% 0%, 40% 100%, 55% 100%, 55% 0%);
    }

    :nth-child(4) {
      clip-path: polygon(60% 0%, 60% 100%, 75% 100%, 75% 0%);
    }

    :last-child {
      clip-path: polygon(80% 0%, 80% 100%, 95% 100%, 95% 0%);
    }
  }
}

</style>
