<template>
  <section class="offer" id="oferta">
    <h1 class="margin-side-mobile">OFERTA</h1>
    <div class="offer-img">
      <img class="offer-img-photo" src="offer.jpg" alt="oferta">
    </div>
    <div class="offer_box margin-side-mobile">
      <p>Strony www i aplikacje mobilne. <br> Dopasowane do <span>Ciebie</span>.</p>
    </div>

    <div class="offer_box offer_box-2 margin-side-mobile">
      <p>Każdy projekt wykonuję z należytą starannością. Szczególną wagę przywiązuję do: jakości kodu, opracowania pod
        kątem RWD oraz zadowolenia klienta.</p>
    </div>

    <div class="offer_box-icons margin-side-mobile">
      <svg width="60" height="54" viewBox="0 0 60 54" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path
          d="M55 0H5C2.23958 0 0 2.26758 0 5.0625V38.8125C0 41.6074 2.23958 43.875 5 43.875H25L23.3333 48.9375H15.8333C14.4479 48.9375 13.3333 50.066 13.3333 51.4688C13.3333 52.8715 14.4479 54 15.8333 54H44.1667C45.5521 54 46.6667 52.8715 46.6667 51.4688C46.6667 50.066 45.5521 48.9375 44.1667 48.9375H36.6667L35 43.875H55C57.7604 43.875 60 41.6074 60 38.8125V5.0625C60 2.26758 57.7604 0 55 0ZM53.3333 37.125H6.66667V6.75H53.3333V37.125Z"
          fill="#CCCCCC"/>
      </svg>

      <svg width="41" height="65" viewBox="0 0 41 65" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path
          d="M34.85 0H6.15C2.75469 0 0 2.72949 0 6.09375V58.9062C0 62.2705 2.75469 65 6.15 65H34.85C38.2453 65 41 62.2705 41 58.9062V6.09375C41 2.72949 38.2453 0 34.85 0ZM20.5 60.9375C18.2322 60.9375 16.4 59.1221 16.4 56.875C16.4 54.6279 18.2322 52.8125 20.5 52.8125C22.7678 52.8125 24.6 54.6279 24.6 56.875C24.6 59.1221 22.7678 60.9375 20.5 60.9375ZM34.85 47.2266C34.85 48.0645 34.1581 48.75 33.3125 48.75H7.6875C6.84188 48.75 6.15 48.0645 6.15 47.2266V7.61719C6.15 6.7793 6.84188 6.09375 7.6875 6.09375H33.3125C34.1581 6.09375 34.85 6.7793 34.85 7.61719V47.2266Z"
          fill="#CCCCCC"/>
      </svg>
    </div>

    <div class="offer_desktop margin-side-desktop margin-side-big">
      <div class="offer_desktop-text">
        <p>Każdy projekt wykonuję z należytą starannością.</p>
        <p>Szczególną wagę przywiązuję do: jakości kodu, opracowania pod kątem RWD oraz zadowolenia klienta.</p>
      </div>

      <div class="offer_desktop-icons">
        <svg width="60" height="54" viewBox="0 0 60 54" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path
            d="M55 0H5C2.23958 0 0 2.26758 0 5.0625V38.8125C0 41.6074 2.23958 43.875 5 43.875H25L23.3333 48.9375H15.8333C14.4479 48.9375 13.3333 50.066 13.3333 51.4688C13.3333 52.8715 14.4479 54 15.8333 54H44.1667C45.5521 54 46.6667 52.8715 46.6667 51.4688C46.6667 50.066 45.5521 48.9375 44.1667 48.9375H36.6667L35 43.875H55C57.7604 43.875 60 41.6074 60 38.8125V5.0625C60 2.26758 57.7604 0 55 0ZM53.3333 37.125H6.66667V6.75H53.3333V37.125Z"
            fill="#CCCCCC"/>
        </svg>

        <svg width="41" height="65" viewBox="0 0 41 65" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path
            d="M34.85 0H6.15C2.75469 0 0 2.72949 0 6.09375V58.9062C0 62.2705 2.75469 65 6.15 65H34.85C38.2453 65 41 62.2705 41 58.9062V6.09375C41 2.72949 38.2453 0 34.85 0ZM20.5 60.9375C18.2322 60.9375 16.4 59.1221 16.4 56.875C16.4 54.6279 18.2322 52.8125 20.5 52.8125C22.7678 52.8125 24.6 54.6279 24.6 56.875C24.6 59.1221 22.7678 60.9375 20.5 60.9375ZM34.85 47.2266C34.85 48.0645 34.1581 48.75 33.3125 48.75H7.6875C6.84188 48.75 6.15 48.0645 6.15 47.2266V7.61719C6.15 6.7793 6.84188 6.09375 7.6875 6.09375H33.3125C34.1581 6.09375 34.85 6.7793 34.85 7.61719V47.2266Z"
            fill="#CCCCCC"/>
        </svg>
      </div>
    </div>

    <TheArrow :goto="'#offerDescribe'" class="offer_box-arrow"></TheArrow>
    <TheArrow :goto="'#offerDescribe'" class="offer_box-arrow-2"></TheArrow>
  </section>
</template>

<script>
import TheArrow from "../UI/TheArrow";

export default {
  name: "Offer",
  components: {TheArrow}
}
</script>

<style scoped lang="scss">
.offer {
  height: 100vh;
  height: calc(var(--vh, 1vh) * 100);
  overflow: hidden;
  position: relative;

  display: flex;
  justify-content: center;

  @include respond(tablets) {
    flex-direction: column;
    justify-content: flex-start;
  }

  h1 {
    position: absolute;
    z-index: 10;
    left: 0;
    top: 13%;
    font-size: clamp(2rem, 3vw, 6rem);

    @include respond(tablets) {
      display: none;
    }
  }

  &-img {
    height: 100%;
    width: 100%;

    @include respond(tablets) {
      position: relative;
      height: 50%;
      width: 100%;
    }

    &-photo {
      height: 100%;
      width: 100%;
      object-fit: cover;
      clip-path: polygon(0% 30%, 100% 0%, 100% 100%, 0% 70%);
      filter: blur(2px);

      @include respond(tablets) {
        clip-path: polygon(0% 0%, 100% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
      }

    }
  }

  &_box {
    color: $color-white;
    position: absolute;
    top: 35%;
    right: 0;
    width: 60%;
    background-color: rgba(#060606, .6);
    font-weight: 600;
    padding: 2rem 1rem;
    border-radius: 31px;
    font-size: clamp(1rem, 3vw, 4rem);
    text-align: center;

    @include respond(tablets) {
      top: auto;
      right: auto;
      margin-top: 15vw;
      font-weight: 500;
      align-self: center;
    }

    span {
      color: $color-blue;
    }

    &-2 {
      top: 50%;
      font-size: clamp(.8rem, 3vw, 2rem);
      font-weight: 400;
      color: rgba($color-white, .9);

      @include respond(tablets) {
        display: none;
      }
    }

    &-icons {
      position: absolute;
      bottom: 15%;
      right: 0;
      display: flex;
      flex-direction: column;
      width: 8rem;

      @include respond(tablets) {
        display: none;
      }

      svg {
        height: 4rem;
        width: 4rem;
      }

      :nth-child(2) {
        align-self: flex-end;
      }
    }

    &-arrow {
      position: absolute;
      bottom: 5%;
    }

    &-arrow-2 {
      position: absolute;
      bottom: 6.5%;
    }

  }

  &_desktop {
    color: $color-black;
    display: none;

    @include respond(tablets) {
      display: flex;
      margin-top: 5rem;
    }

    &-text {
      font-weight: 400;
      font-size: clamp(2rem, 1.5vw, 5rem);
      width: 60%;

      :first-child {
        margin-bottom: 4rem;
      }
    }

    &-icons {
      width: 14rem;
      display: flex;
      flex-direction: column;
      flex: 1;
      align-items: flex-end;
      margin-right: 2vw;

      @include respond(mega-big) {
        width: 20rem;
      }

      svg {
        height: 8rem;
        width: 8rem;

        @include respond(mega-big) {
          height: 10rem;
          width: 10rem;
        }
      }

      :first-child {
        margin-right: 5rem;
      }
    }

  }
}


</style>
