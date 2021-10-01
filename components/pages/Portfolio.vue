<template>
  <section class="portfolio">
    <h1 class="portfolio-header">PORTFOLIO</h1>

    <transition-group class="portfolio_projects" name="portfolio">
      <div class="portfolio_projects_box" v-for="project in projectsLimit" :key="project.src">
        <picture>
          <source class="portfolio_projects_box-img" :srcset="project.src + '.webp'" type="image/webp">
          <img class="portfolio_projects_box-img" :src="project.src + '.png'" alt="portfolio">
        </picture>
        <div class="portfolio_projects_box-description">
          <h1>{{ project.nazwa }}</h1>
          <div class="technologies">
            <h2>Technologie: </h2>
            <p v-for="technology in project.technologies">
              {{ technology }}
            </p>
          </div>

          <div class="portfolio_projects_box-circle">
            <a v-if="project.github" class="portfolio_projects_box-github" :href="project.github">
              <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="github-square"
                   class="svg-inline--fa fa-github-square fa-w-14" role="img" xmlns="http://www.w3.org/2000/svg"
                   viewBox="0 0 448 512">
                <path
                  d="M400 32H48C21.5 32 0 53.5 0 80v352c0 26.5 21.5 48 48 48h352c26.5 0 48-21.5 48-48V80c0-26.5-21.5-48-48-48zM277.3 415.7c-8.4 1.5-11.5-3.7-11.5-8 0-5.4.2-33 .2-55.3 0-15.6-5.2-25.5-11.3-30.7 37-4.1 76-9.2 76-73.1 0-18.2-6.5-27.3-17.1-39 1.7-4.3 7.4-22-1.7-45-13.9-4.3-45.7 17.9-45.7 17.9-13.2-3.7-27.5-5.6-41.6-5.6-14.1 0-28.4 1.9-41.6 5.6 0 0-31.8-22.2-45.7-17.9-9.1 22.9-3.5 40.6-1.7 45-10.6 11.7-15.6 20.8-15.6 39 0 63.6 37.3 69 74.3 73.1-4.8 4.3-9.1 11.7-10.6 22.3-9.5 4.3-33.8 11.7-48.3-13.9-9.1-15.8-25.5-17.1-25.5-17.1-16.2-.2-1.1 10.2-1.1 10.2 10.8 5 18.4 24.2 18.4 24.2 9.7 29.7 56.1 19.7 56.1 19.7 0 13.9.2 36.5.2 40.6 0 4.3-3 9.5-11.5 8-66-22.1-112.2-84.9-112.2-158.3 0-91.8 70.2-161.5 162-161.5S388 165.6 388 257.4c.1 73.4-44.7 136.3-110.7 158.3zm-98.1-61.1c-1.9.4-3.7-.4-3.9-1.7-.2-1.5 1.1-2.8 3-3.2 1.9-.2 3.7.6 3.9 1.9.3 1.3-1 2.6-3 3zm-9.5-.9c0 1.3-1.5 2.4-3.5 2.4-2.2.2-3.7-.9-3.7-2.4 0-1.3 1.5-2.4 3.5-2.4 1.9-.2 3.7.9 3.7 2.4zm-13.7-1.1c-.4 1.3-2.4 1.9-4.1 1.3-1.9-.4-3.2-1.9-2.8-3.2.4-1.3 2.4-1.9 4.1-1.5 2 .6 3.3 2.1 2.8 3.4zm-12.3-5.4c-.9 1.1-2.8.9-4.3-.6-1.5-1.3-1.9-3.2-.9-4.1.9-1.1 2.8-.9 4.3.6 1.3 1.3 1.8 3.3.9 4.1zm-9.1-9.1c-.9.6-2.6 0-3.7-1.5s-1.1-3.2 0-3.9c1.1-.9 2.8-.2 3.7 1.3 1.1 1.5 1.1 3.3 0 4.1zm-6.5-9.7c-.9.9-2.4.4-3.5-.6-1.1-1.3-1.3-2.8-.4-3.5.9-.9 2.4-.4 3.5.6 1.1 1.3 1.3 2.8.4 3.5zm-6.7-7.4c-.4.9-1.7 1.1-2.8.4-1.3-.6-1.9-1.7-1.5-2.6.4-.6 1.5-.9 2.8-.4 1.3.7 1.9 1.8 1.5 2.6z"></path>
              </svg>
            </a>

            <a v-if="project.href" class="portfolio_projects_box-circle" :href="project.href">
              <svg viewBox="0 0 59 59" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M29.5 0.921875C45.2871 0.921875 58.0781 13.7129 58.0781 29.5C58.0781 45.2871 45.2871 58.0781 29.5 58.0781C13.7129 58.0781 0.921875 45.2871 0.921875 29.5C0.921875 13.7129 13.7129 0.921875 29.5 0.921875ZM26.1697 17.4695L34.8699 25.8125H13.8281C12.2955 25.8125 11.0625 27.0455 11.0625 28.5781V30.4219C11.0625 31.9545 12.2955 33.1875 13.8281 33.1875H34.8699L26.1697 41.5305C25.052 42.6021 25.0289 44.3883 26.1236 45.483L27.3912 46.7391C28.4744 47.8223 30.226 47.8223 31.2977 46.7391L46.5893 31.459C47.6725 30.3758 47.6725 28.6242 46.5893 27.5525L31.2977 12.2494C30.2145 11.1662 28.4629 11.1662 27.3912 12.2494L26.1236 13.5055C25.0289 14.6117 25.052 16.3979 26.1697 17.4695Z"/>
              </svg>
            </a>
          </div>

        </div>
      </div>
    </transition-group>

    <the-button v-if="isProjects" @click="loadMore()" class="portfolio_projects-button">Załaduj więcej</the-button>
    <the-arrow :goto="'#oferta'" class="portfolio_projects-arrow"></the-arrow>
  </section>
</template>

<script>
import TheButton from "../UI/TheButton";
import TheArrow from "../UI/TheArrow";

export default {
  name: "Portfolio",
  components: {TheArrow, TheButton},
  data() {
    return {
      isProjects: true,
      projects: [
        {
          nazwa: "Termobudowa",
          technologies: ['Vue', 'Vuetify'],
          src: "termobudowa",
          href: "http://termobudowa.com.pl"
        },
        {
          nazwa: "Desite",
          technologies: ['Vue'],
          src: "desite",
          href: "http://testdesite.ct8.pl"
        },
        {
          nazwa: "Łapiemy Szczyty",
          technologies: ['Vue', 'Express', 'MongoDB'],
          src: "lapiemyszczyty",
          href: "https://lapiemyszczyty.pl",
          github: "https://github.com/Cersin/Lapiemy-Szczyty"
        },
        {
          nazwa: "Mountains",
          technologies: ['HTML', 'SCSS'],
          src: "mountains",
          href: "https://cersin.github.io/Mountains/",
          github: "https://github.com/Cersin/Mountains"
        },
        {
          nazwa: "Portfolio",
          technologies: ['Nuxt'],
          src: "portfolio",
          href: "https://cersin.github.io/Portfolio-Szymon/",
          github: "https://github.com/Cersin/Portfolio-Szymon"
        },
        {
          nazwa: "Walutomierz",
          technologies: ['Ionic', 'Angular'],
          src: "walutomierz",
          github: "https://github.com/Cersin/WSBWalutomierz"
        },
        {
          nazwa: "WeatherApp",
          technologies: ['Ionic', 'Vue'],
          src: "weather",
          github: "https://github.com/Cersin/ionic-weatherapp"
        },
        {
          nazwa: "Znajdź trenera",
          technologies: ['Vue', 'Vuex'],
          src: "znajdztrenera",
          href: "https://cersin.github.io/znajdztrenera/"
        },
        {
          nazwa: "MyHotel",
          technologies: ['Nativescript', 'Angular', 'Firebase'],
          src: "myhotel",
          github: "https://github.com/Cersin/MyHotel"
        },
        {
          nazwa: "Przecięcie odcinków",
          technologies: ['HTML', 'CSS', 'JS'],
          src: "przeciecie",
          href: "https://cersin.github.io/PrzeciecieOdcinkow/",
          github: "https://github.com/Cersin/PrzeciecieOdcinkow"
        },
        {
          nazwa: "Nexter",
          technologies: ['HTML', 'SCSS'],
          src: "nexter",
          href: "https://cersin.github.io/Nexter/",
          github: "https://github.com/Cersin/Nexter"
        },
        {
          nazwa: "Trillo",
          technologies: ['HTML', 'SCSS'],
          src: "trillo",
          href: "https://cersin.github.io/Trillo/",
          github: "https://github.com/Cersin/Trillo"
        }
      ],
      limit: 2
    }
  },
  computed: {
    projectsLimit() {
      return this.limit ? this.projects.slice(0, this.limit) : this.projects
    }
  },
  methods: {
    loadMore() {
      this.limit = this.limit + 2;
      if (this.limit >= this.projects.length) {
        this.isProjects = false;
      }
    }
  }
}
</script>

<style scoped lang="scss">
.portfolio {
  min-height: 100vh;
  min-height: calc(var(--vh, 1vh) * 100);
  color: $color-black;

  display: flex;
  flex-direction: column;

  &-header {
    padding-top: 10vh;
    margin-bottom: 5vh;
    color: $color-blue;
    font-weight: bold;
    font-size: clamp(2rem, 3vw, 4rem);

    @include respond(tablets) {
      margin-left: 20%;
    }
  }

  &_projects {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 3rem;
    column-gap: 8rem;
    flex: 1;
    color: $color-white;

    @include respond(tablets) {
      gap: 6rem;
    }

    &_box {
      position: relative;
      height: clamp(170px, 30vw, 400px);
      width: clamp(170px, 30vw, 400px);

      &:hover &-description {
        display: grid;
      }

      &:after {
        content: '';
        position: absolute;
        background-color: $color-blue;
        top: 18%;
        left: 8%;
        height: 90%;
        width: 100%;
        z-index: -1;
      }

      &-github {
        fill: $color-white;

        :hover, :active {
          fill: $color-black;
        }

        svg {
          height: clamp(3rem, 4vw, 6rem);
          width: clamp(3rem, 4vw, 6rem);
        }
      }

      &-img {
        height: 100%;
        width: 100%;
      }

      &-circle {
        align-self: end;
        justify-self: end;
        margin-right: .5rem;
        margin-bottom: .5rem;

        svg {
          height: clamp(3rem, 4vw, 6rem);
          width: clamp(3rem, 4vw, 6rem);
          fill: $color-white;
          transition: .3s;

          &:hover, &:active {
            fill: $color-blue;
          }
        }
      }

      &-description {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        background: linear-gradient(180deg, $color-linear-3 0%, rgba(155, 71, 218, 0.88) 3.12%, rgba(102, 84, 231, 0.88) 50.52%, rgba(0, 59, 146, 0.88) 100%);
        display: grid;

        @include respond(medium) {
          display: none;
        }

        h1 {
          display: flex;
          margin-top: 1rem;
          margin-left: 1rem;
          font-size: clamp(1.5rem, 2vw, 3rem);
        }

        .technologies {
          margin-left: 1rem;
          font-size: clamp(1rem, 1.5vw, 2rem);
        }
      }
    }

    &-button {
      align-self: center;
      margin-top: 5vh;
    }

    &-arrow {
      margin: 5vh 0;
    }
  }
}

.portfolio-item {
  display: flex;
}

.portfolio-enter-active, .portfolio-leave-active {
  transition: all 1s;
}

.portfolio-enter, .portfolio-leave-to /* .list-leave-active below version 2.1.8 */
{
  opacity: 0;
  transform: translateY(30px);
}
</style>
