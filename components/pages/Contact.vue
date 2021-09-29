<template>
  <section class="contact">
    <header>zapraszam do <span>kontaktu</span></header>
    <the-socials class="contact-socials"></the-socials>
    <img src="me3-mobile.png" alt="photo of me" class="contact-photo">
    <img src="me3.png" alt="photo of me" class="contact-photo-desktop">
    <form v-if="!isSend" class="contact_form" id="form" @submit.prevent="sendEmail">
      <div class="contact_form_box">
        <div class="contact_form_box-input">
          <input type="text" required name="user_name">
          <p class="imie">Imię i nazwisko</p>
        </div>
        <div class="contact_form_box-input">
          <input type="email" required name="user_email">
          <p>E-mail</p>
        </div>
        <div class="contact_form_box-input">
          <textarea required name="message"></textarea>
          <p>Treść</p>
        </div>
      </div>
      <div class="contact_form-button">
        <the-button id="form_button">wyślij</the-button>
        <the-socials class="contact_form-button-socials_desktop"></the-socials>
      </div>
    </form>
    <div v-if="isSend" class="contact-success">
      <h1>Wiadomość wysłana, dziękuję za kontakt.</h1>
    </div>
    <the-spinner v-if="isSending"></the-spinner>
    <the-arrow :direction="'up'"></the-arrow>
  </section>
</template>

<script>
import TheSocials from "../TheSocials";
import emailjs from 'emailjs-com';
import TheButton from "../UI/TheButton";
import TheSpinner from "../UI/TheSpinner";
import TheArrow from "../UI/TheArrow";

export default {
  name: "Contact",
  components: {TheArrow, TheSpinner, TheButton, TheSocials},
  data() {
    return {
      isSend: false,
      isSending: false
    }
  },
  methods: {
    async sendEmail(e) {
      this.isSending = true;
      try {
        let email = await emailjs.sendForm(process.env.EMAIL_SERVICE_ID, process.env.EMAIL_SERVICE_TEMPLATE, e.target, process.env.EMAIL_SERVICE_USER);
        this.isSend = true;
        this.isSending = false;
        document.getElementById('form').style.display = 'none';
      } catch (error) {
        this.isSending = false;
        console.log('FAILED...', error);
        alert('Wystąpił błąd');
      }
    }
  }
}
</script>

<style scoped lang="scss">
.contact {
  height: 100vh;
  height: calc(var(--vh, 1vh) * 100);

  display: grid;
  grid-template-areas:
                        "header header"
                        "socials photo"
                        "form form"
                        "arrow arrow";
  grid-template-columns:1fr;
  grid-template-rows: 20vh auto 1fr 10vh;
  justify-items: center;
  align-items: center;

  @include respond(tablets) {
    grid-template-areas:
                        "header photo"
                        "form photo"
                        "arrow arrow";
    grid-template-rows: 30% 1fr 10vh;
    grid-template-columns: 1fr 30vw;
    margin: 0;
  }

  header {
    grid-area: header;
    text-transform: uppercase;
    font-weight: bold;
    font-size: clamp(2rem, 3vw, 6rem);

    @include respond(tablets) {
      align-self: end;
      margin-bottom: 2rem;
    }

    span {
      color: $color-blue;
    }
  }

  &-socials {
    grid-area: socials;

    @include respond(tablets) {
      display: none;
    }
  }

  &-photo {
    grid-area: photo;
    height: 20vh;
    width: auto;
    border-radius: 5rem;

    @include respond(tablets) {
      display: none;
    }

    &-desktop {
      display: none;

      @include respond(tablets) {
        display: block;
        grid-area: photo;
        height: 100%;
        width: auto;
        justify-self: end;
      }
    }
  }

  &_form {
    grid-area: form;
    width: 100%;
    display: flex;
    flex-direction: column;

    @include respond(tablets) {
      width: 60%;
      align-self: start;
    }

    &_box {
      width: 100%;
      position: relative;
      background-color: $color-purple;
      display: flex;
      flex-direction: column;
      align-items: center;
      border-radius: 20px;
      font-size: clamp(1rem, 1.7vw, 2rem);

      @include respond(tablets) {
        background-color: transparent;
      }

      &:after {
        content: '';
        position: absolute;
        z-index: -1;
        width: 100%;
        height: 100%;
        background-color: $color-darkblue;
        border-radius: 20px;
        transform: translate(5%, 10%);

        @include respond(tablets) {
          display: none;
        }
      }

      :first-child {
        padding-top: 1rem;
      }

      :not(:last-child) {
        margin-bottom: 1rem;
      }

      &-input {
        width: 90%;
        display: flex;
        flex-direction: column;
        align-items: flex-start;

        p {
          color: $color-white;
          font-weight: 700;
          order: -1;

          @include respond(tablets) {
            color: $color-black;
            font-weight: 600;
          }
        }

        input {
          width: 100%;
          background: transparent;
          border: none;
          border-bottom: 1px solid $color-white;
          padding-bottom: .5rem;
          color: $color-white;

          @include respond(tablets) {
            border-bottom: 1px solid $color-black;
            color: $color-black;
          }
        }

        textarea {
          width: 100%;
          background: transparent;
          resize: none;
          border: none;
          border-bottom: 1px solid $color-white;
          margin-bottom: 2rem;
          color: $color-white;

          @include respond(tablets) {
            border-bottom: 1px solid $color-black;
            min-height: 20vh;
            color: $color-black;

          }
        }
      }

    }

    &-button {
      align-self: flex-end;
      margin-top: 10%;

      @include respond(tablets) {
        display: flex;
        width: 90%;
        align-self: center;
      }

      &-socials_desktop {
        display: none;

        @include respond(tablets) {
          display: flex;
          flex: 1;
          justify-content: flex-end;
        }
      }
    }
  }

  &-success {
    grid-area: form;
    color: $color-blue;
    text-align: center;
    font-size: clamp(2rem, 3vw, 6rem);
    width: 100%;
  }
}

input:focus + p, textarea:focus + p {
  transition: all .2s;
  color: $color-blue;

  @include respond(tablets) {
    transition: all .2s;
    color: $color-blue;
  }
}

</style>
