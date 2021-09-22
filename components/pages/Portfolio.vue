<template>
  <section class="portfolio" id="portfolio">
    <h1 class="portfolio-header">PORTFOLIO</h1>

    <div class="portfolio_projects">
      <div class="portfolio_projects_box" v-for="project in projectsLimit">
        <img class="portfolio_projects_box-img" :src="project.src" alt="portfolio">
        <div class="portfolio_projects_box-description">
          <h1>{{ project.nazwa }}</h1>
          <div class="technologies">
            <h2>Technologie: </h2>
            <p v-for="technology in project.technologies">
              {{ technology }}
            </p>
          </div>
          <a class="portfolio_projects_box-circle" :href="project.href">
            <svg viewBox="0 0 59 59" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M29.5 0.921875C45.2871 0.921875 58.0781 13.7129 58.0781 29.5C58.0781 45.2871 45.2871 58.0781 29.5 58.0781C13.7129 58.0781 0.921875 45.2871 0.921875 29.5C0.921875 13.7129 13.7129 0.921875 29.5 0.921875ZM26.1697 17.4695L34.8699 25.8125H13.8281C12.2955 25.8125 11.0625 27.0455 11.0625 28.5781V30.4219C11.0625 31.9545 12.2955 33.1875 13.8281 33.1875H34.8699L26.1697 41.5305C25.052 42.6021 25.0289 44.3883 26.1236 45.483L27.3912 46.7391C28.4744 47.8223 30.226 47.8223 31.2977 46.7391L46.5893 31.459C47.6725 30.3758 47.6725 28.6242 46.5893 27.5525L31.2977 12.2494C30.2145 11.1662 28.4629 11.1662 27.3912 12.2494L26.1236 13.5055C25.0289 14.6117 25.052 16.3979 26.1697 17.4695Z"/>
            </svg>
          </a>
        </div>
      </div>
    </div>

    <the-button @click="loadMore()" class="portfolio_projects-button">Załaduj więcej</the-button>
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
      projects: [
        {
          nazwa: "Termobudowa",
          technologies: ['Vue', 'Vuetify'],
          src: "portfolio-1.png",
          href: "http://termobudowa.com.pl"
        },
        {
          nazwa: "Łapiemy Szczyty",
          technologies: ['Vue', 'Express', 'MongoDB'],
          src: "portfolio-2.png",
          href: "https://lapiemyszczyty.pl"
        },
        {
          nazwa: "Taki tam",
          technologies: ['HTML', 'SASS'],
          src: "portfolio-3.png",
          href: "https://lapiemyszczyty.pl"
        },
        {
          nazwa: "Łapiemy Szczyty",
          technologies: ['Vue', 'Express', 'MongoDB'],
          src: "portfolio-2.png",
          href: "https://lapiemyszczyty.pl"
        },
        {
          nazwa: "Taki tam",
          technologies: ['HTML', 'SASS'],
          src: "portfolio-3.png",
          href: "https://lapiemyszczyty.pl"
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
    }
  }
}
</script>

<style scoped lang="scss">
.portfolio {
  min-height: 100vh;
  min-height: calc(var(--vh, 1vh) * 100);

  display: flex;
  flex-direction: column;

  &-header {
    padding-top: 10vh;
    margin-bottom: 5vh;
    color: $color-blue;
    font-weight: bold;
    font-size: clamp(3rem, 3vw, 6rem);

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

    &_box {
      position: relative;
      height: clamp(200px, 25vw, 400px);
      width: clamp(200px, 25vw, 400px);

      &:hover  &-description  {
        display: flex;
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

      &-img {
        height: 100%;
        width: 100%;
      }

      &-circle {
        align-self: flex-end;
        margin-right: 1rem;
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
        display: flex;
        flex-direction: column;
        justify-content: space-between;

        @include respond(medium) {
          display: none;
        }

        h1 {
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

</style>
