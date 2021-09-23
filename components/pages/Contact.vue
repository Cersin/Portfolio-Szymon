<template>
  <section class="contact" id="kontakt">
    <header>zapraszam do <span>kontaktu</span></header>
    <the-socials class="contact-socials"></the-socials>
    <img src="me3-mobile.png" alt="photo of me" class="contact-photo">
    <img src="me3.png" alt="photo of me" class="contact-photo-desktop">
    <form class="contact_form" @submit.prevent="sendEmail">
      <div class="contact_form_box">
        <div class="contact_form_box-input">
          <p>Imię i nazwisko</p>
          <input type="text" required name="user_name">
        </div>
        <div class="contact_form_box-input">
          <p>E-mail</p>
          <input type="email" required name="user_email">
        </div>
        <div class="contact_form_box-input">
          <p>Treść</p>
          <textarea required name="message"></textarea>
        </div>
      </div>
      <the-button class="contact_form-button">wyślij</the-button>
    </form>
  </section>
</template>

<script>
import TheSocials from "../TheSocials";
import emailjs from 'emailjs-com';
import TheButton from "../UI/TheButton";

export default {
  name: "Contact",
  components: {TheButton, TheSocials},
  data() {
    return {
      isSend: false
    }
  },
  methods: {
    sendEmail(e) {
      emailjs.sendForm('service_275ecft', 'template_dm2kels', e.target, 'user_Glrid5hQCnoIO9RCdwtRz')
        .then((result) => {
          this.isSend = true;
          console.log('SUCCESS!', result.status, result.text);
        }, (error) => {
          this.$toast.error(this.$t('contact.error'));
          console.log('FAILED...', error);
        });
    }
  },
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
                        "button button";
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 20vh auto 1fr auto;
  justify-items: center;
  align-items: center;

  header {
    grid-area: header;
    text-transform: uppercase;
    font-weight: bold;
    font-size: clamp(1.8rem, 1.7vw, 3rem);

    span {
      color: $color-blue;
    }
  }

  &-socials {
    grid-area: socials;
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
      }
    }
  }

  &_form {
    grid-area: form;
    width: 100%;
    display: flex;
    flex-direction: column;

    &_box {
      width: 100%;
      position: relative;
      background-color: $color-purple;
      display: flex;
      flex-direction: column;
      align-items: center;
      border-radius: 20px;

      &:after {
        content: '';
        position: absolute;
        z-index: -1;
        width: 100%;
        height: 100%;
        background-color: $color-darkblue;
        border-radius: 20px;
        transform: translate(5%, 10%);
      }

      :first-child {
        padding-top: 1rem;
      }

      :not(:last-child){
        margin-bottom: 1rem;
      }

      &-input {
        width: 90%;
        align-items: center;

        p {
          color: $color-white;
          font-weight: 500;
        }

        input {
          width: 100%;
          background: transparent;
          border: none;
          border-bottom: 1px solid $color-white;
          padding-bottom: .5rem;

        }

        textarea {
          width: 100%;
          background: transparent;
          resize: none;
          border: none;
          border-bottom: 1px solid $color-white;
          margin-bottom: 2rem;
        }
      }

    }

    &-button {
      align-self: flex-end;
      margin-top: 10%;
    }
  }

}

</style>
