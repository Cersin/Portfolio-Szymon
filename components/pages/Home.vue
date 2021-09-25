<template>
  <section class="wrapper" id="home">
    <div class="home">
      <div class="home_description">
        <p class="home_description-hi">Cześć, nazywam się</p>
        <p class="home_description-name">SZYMON WÓJCIK.</p>
        <p class="home_description-developer">Jestem <span>Front-end Developerem</span>.</p>
        <the-button class="home_description-button"><a href="#kontakt">Podejmij współpracę</a></the-button>
        <the-socials class="home_description-socials"></the-socials>
      </div>

      <div class="home_photo">
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
      </div>
    </div>

    <the-arrow :goto="'#about'"></the-arrow>

  </section>
</template>

<script>
import TheButton from "../UI/TheButton";
import TheSocials from "../TheSocials";
import TheArrow from "../UI/TheArrow";

export default {
  name: "Home",
  components: {TheArrow, TheSocials, TheButton}
}
</script>

<style scoped lang="scss">
.wrapper {
  height: 100vh;
  height: calc(var(--vh, 1vh) * 100);
  display: flex;
  flex-direction: column;
}

.home {
  height: 90%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  font-weight: 600;

  a {
    text-decoration: none;
    color: $color-white;
  }

  @media only screen and (max-height: 750px) {
    padding-top: 4rem;
  }

  @media only screen and (max-height: 600px) {
    padding-top: 6rem;
  }

  @include respond(tablets) {
    flex-direction: row;
    align-items: center;
  }


  &_description {
    display: flex;
    flex-direction: column;
    justify-content: center;

    @include respond(tablets) {
      width: 50%;
    }

    &-button {
      align-self: end;
      margin-top: 2rem;

      @include respond(tablets) {
        align-self: flex-start;
        margin-top: 10vh;
      }
    }

    &-socials {
      align-self: flex-end;
      margin-top: 1rem;

      @include respond(tablets) {
        align-self: flex-start;
        margin-top: 10vh;
      }
    }

    :not(:last-child) {
      margin-bottom: 3px;
    }

    &-hi {
      font-size: clamp(1.8rem, 1.7vw, 3rem);
    }

    &-name {
      font-size: clamp(3rem, 3vw, 5rem);
    }

    &-developer {
      font-size: clamp(1.8rem, 1.7vw, 3.3rem);
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
    margin-left: 7%;
    display: flex;
    justify-content: center;
    align-self: flex-start;

    @include respond(tablets) {
      width: 50%;
      height: 90%;
      top: 10%;
    }

    > * {
      display: flex;
      position: absolute;
      height: 100%;
      width: 100%;
      background-image: url("static/me.png");
      background-position: 35% 70%;
      background-size: 600px;
      background-repeat: no-repeat;

      @include respond(tablets) {
        background-size: cover;
        background-position: 35% 80%;
      }
    }

    :first-child {
      clip-path: polygon(0% 30%, 0% 80%, 15% 80%, 15% 30%);
      animation: polygon-mobile-1 .5s;
      animation-delay: 1s;
      animation-fill-mode: both;
    }

    :nth-child(2) {
      clip-path: polygon(18% 25%, 18% 90%, 33% 90%, 33% 25%);
      animation: polygon-mobile-2 .5s;
      animation-delay: .5s;
      animation-fill-mode: both;
    }

    :nth-child(3) {
      clip-path: polygon(36% 15%, 36% 95%, 51% 95%, 51% 15%);
      animation: polygon-mobile-3 .5s;
      animation-fill-mode: both;
    }

    :nth-child(4) {
      clip-path: polygon(54% 20%, 54% 90%, 69% 90%, 69% 20%);
      animation: polygon-mobile-4 .5s;
      animation-delay: .5s;
      animation-fill-mode: both;
    }

    :last-child {
      clip-path: polygon(72% 25%, 72% 80%, 87% 80%, 87% 25%);
      animation: polygon-mobile-5 .5s;
      animation-delay: 1s;
      animation-fill-mode: both;
    }

    @include respond(tablets) {
      :first-child {
        clip-path: polygon(0% 40%, 0% 80%, 16% 80%, 16% 40%);
        animation: polygon1 .5s;
        animation-delay: 1s;
        animation-fill-mode: both;
      }

      :nth-child(2) {
        clip-path: polygon(18% 15%, 18% 95%, 34% 95%, 34% 15%);
        animation: polygon2 .5s;
        animation-delay: .5s;
        animation-fill-mode: both;
      }

      :nth-child(3) {
        clip-path: polygon(36% 5%, 36% 100%, 52% 100%, 52% 5%);
        animation: polygon3 .5s;
        animation-fill-mode: both;
      }

      :nth-child(4) {
        clip-path: polygon(54% 18%, 54% 88%, 70% 88%, 70% 18%);
        animation: polygon4 .5s;
        animation-delay: .5s;
        animation-fill-mode: both;
      }

      :last-child {
        clip-path: polygon(72% 25%, 72% 75%, 88% 75%, 88% 25%);
        animation: polygon5 .5s;
        animation-delay: 1s;
        animation-fill-mode: both;
      }
    }
  }

}

</style>
