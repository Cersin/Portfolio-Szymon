<template>
  <section class="home">
    <div class="home_description">
      <p class="home_description-hi">Cześć, nazywam się</p>
      <p class="home_description-name">SZYMON WÓJCIK.</p>
      <p class="home_description-developer">Jestem <span>Front-end Developerem</span>.</p>
      <the-button class="home_description-button">Podejmij współpracę</the-button>
      <the-socials class="home_description-socials"></the-socials>


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
import TheButton from "../UI/TheButton";
import TheSocials from "../TheSocials";

export default {
  name: "Home",
  components: {TheSocials, TheButton}
}
</script>

<style scoped lang="scss">
.home {
  display: flex;
  flex-direction: column;
  height: 100vh;
  justify-content: space-evenly;

  @media only screen and (max-height: 750px) {
    padding-top: 4rem;
  }

  @media only screen and (max-height: 600px) {
    padding-top: 6rem;
  }


  &_description {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 50%;

    &-button {
      align-self: end;
      margin-top: 2rem;
    }

    &-socials {
      align-self: flex-end;
      margin-top: 1rem;
    }

    :not(:last-child) {
      margin-bottom: 3px;
    }

    &-hi {
      font-size: clamp(1.8rem, 1.8vw, 3.3rem);
    }

    &-name {
      font-size: clamp(3rem, 6vw, 7rem);
      //font-size: 70px;
    }

    &-developer {
      font-size: clamp(1.8rem, 1.8vw, 3.3rem);
      //font-size: 35px;

      span {
        color: $color-blue;
        font-weight: bold;
      }
    }
  }


  &_photo {
    position: relative;
    height: 60%;
    width: 100%;
    margin-left: 7%;

    > * {
      display: flex;
      position: absolute;
      height: 100%;
      width: 100%;
      background-image: url("static/me.png");
      background-position: 35% 70%;
      background-size: 600px;
      background-repeat: no-repeat;
    }

    :first-child {
      clip-path: polygon(0% 30%, 0% 80%, 15% 80%, 15% 30%);
      animation: fromLeft .5s ease-in-out;
      animation-delay: .6s;
      animation-fill-mode: both;
    }

    :nth-child(2) {
      clip-path: polygon(18% 25%, 18% 90%, 33% 90%, 33% 25%);
      animation: fromLeft .5s ease-in-out;
      animation-delay: .3s;
      animation-fill-mode: both;

    }

    :nth-child(3) {
      clip-path: polygon(36% 15%, 36% 95%, 51% 95%, 51% 15%);
      animation: fromLeft .5s ease-in-out;
      animation-fill-mode: both;

    }

    :nth-child(4) {
      clip-path: polygon(54% 20%, 54% 90%, 69% 90%, 69% 20%);
      animation: fromRight .5s ease-in-out;
      animation-delay: .3s;
      animation-fill-mode: both;

    }

    :last-child {
      clip-path: polygon(72% 25%, 72% 80%, 87% 80%, 87% 25%);
      animation: fromRight .5s ease-in-out;
      animation-delay: .6s;
      animation-fill-mode: both;

    }
  }
}

</style>
