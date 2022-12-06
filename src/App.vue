<template>
  <div v-if="loading" class="page-preload">
    <div>
      <div>Quack</div>
      <div>Quack</div>
    </div>
  </div>

  <TransitionRoot :show="!loading">
    <div class="page-container">
      <div class="migration-status">
        <div class="container container--large"><b>Migration status: 2034/5000</b> (last updated 10/27)</div>
        <span style="width: 40%;"></span>
      </div>
      <div class="header">
        <div
          class="container container--flex container--flex-ch container--large"
        >

          <div class="header__nav">
            <ul>

              <li><a href="https://migrate.cryptoduckies.co" target="_blank">Migrate</a></li>
              <li><a href="#roadmap">Roadmap</a></li>
              <li><a href="#team">Team</a></li>
              <li><a href="#attributes">Gallery</a></li>
            </ul>
          </div>

          <div class="header__logo">Crypto Duckies <span>Sold out!</span></div>

          <div class="header__socials">
            <a
              href="https://www.twitter.com/DuckiesCrypto"
              target="_blank"
              class="button button--round button--icon"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="currentColor"
                viewBox="0 0 16 16"
              >
                <path
                  d="M5.026 15c6.038 0 9.341-5.003 9.341-9.334 0-.14 0-.282-.006-.422A6.685 6.685 0 0 0 16 3.542a6.658 6.658 0 0 1-1.889.518 3.301 3.301 0 0 0 1.447-1.817 6.533 6.533 0 0 1-2.087.793A3.286 3.286 0 0 0 7.875 6.03a9.325 9.325 0 0 1-6.767-3.429 3.289 3.289 0 0 0 1.018 4.382A3.323 3.323 0 0 1 .64 6.575v.045a3.288 3.288 0 0 0 2.632 3.218 3.203 3.203 0 0 1-.865.115 3.23 3.23 0 0 1-.614-.057 3.283 3.283 0 0 0 3.067 2.277A6.588 6.588 0 0 1 .78 13.58a6.32 6.32 0 0 1-.78-.045A9.344 9.344 0 0 0 5.026 15z"
                />
              </svg>
            </a>

            <a
              href="https://discord.gg/jn35YkYEjj"
              target="_blank"
              class="button button--round button--icon"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="currentColor"
                viewBox="0 0 16 16"
              >
                <path
                  d="M6.552 6.712c-.456 0-.816.4-.816.888s.368.888.816.888c.456 0 .816-.4.816-.888.008-.488-.36-.888-.816-.888zm2.92 0c-.456 0-.816.4-.816.888s.368.888.816.888c.456 0 .816-.4.816-.888s-.36-.888-.816-.888z"
                />
                <path
                  d="M13.36 0H2.64C1.736 0 1 .736 1 1.648v10.816c0 .912.736 1.648 1.64 1.648h9.072l-.424-1.48 1.024.952.968.896L15 16V1.648C15 .736 14.264 0 13.36 0zm-3.088 10.448s-.288-.344-.528-.648c1.048-.296 1.448-.952 1.448-.952-.328.216-.64.368-.92.472-.4.168-.784.28-1.16.344a5.604 5.604 0 0 1-2.072-.008 6.716 6.716 0 0 1-1.176-.344 4.688 4.688 0 0 1-.584-.272c-.024-.016-.048-.024-.072-.04-.016-.008-.024-.016-.032-.024-.144-.08-.224-.136-.224-.136s.384.64 1.4.944c-.24.304-.536.664-.536.664-1.768-.056-2.44-1.216-2.44-1.216 0-2.576 1.152-4.664 1.152-4.664 1.152-.864 2.248-.84 2.248-.84l.08.096c-1.44.416-2.104 1.048-2.104 1.048s.176-.096.472-.232c.856-.376 1.536-.48 1.816-.504.048-.008.088-.016.136-.016a6.521 6.521 0 0 1 4.024.752s-.632-.6-1.992-1.016l.112-.128s1.096-.024 2.248.84c0 0 1.152 2.088 1.152 4.664 0 0-.68 1.16-2.448 1.216z"
                />
              </svg>
            </a>
          </div>
        </div>
      </div>

      <div class="hero">
        <div class="container container--large">
          <h1 class="hero__title page-title">
            Quack Quack, <br />
            Join the flock
          </h1>
        </div>
        <div class="container">
          <div class="hero__content">
            <p>
              Adopt yourself a Duckie and join The Flock. Each Duck is a 1 of 1
              programmatically generated with a completely unique combination of
              traits. No two are identical. Only 5000 Duckies will ever exist.
            </p>

            <div class="hero__button-group">
              <a
                href="https://opensea.io/collection/crypto-duckies"
                class="button"
                target="_blank"
              >
                Buy on OpenSea
              </a>
              <a
                href="https://discord.gg/jn35YkYEjj"
                class="button button--purple"
                target="_blank"
              >
                Join our Discord
              </a>
            </div>
          </div>
        </div>
      </div>

      <div class="duckie-marquee">
        <div class="duckie-marquee__container">
          <img src="./assets/img/1.png" />
          <img src="./assets/img/2.png" />
          <img src="./assets/img/3.png" />
          <img src="./assets/img/4.png" />
          <img src="./assets/img/5.png" />
          <img src="./assets/img/7.png" />
          <img src="./assets/img/8.png" />
          <img src="./assets/img/6.png" />
          <img src="./assets/img/9.png" />
          <img src="./assets/img/10.png" />
          <img src="./assets/img/11.png" />
          <img src="./assets/img/12.png" />
        </div>
        <div class="duckie-marquee__container">
          <img src="./assets/img/1.png" />
          <img src="./assets/img/2.png" />
          <img src="./assets/img/3.png" />
          <img src="./assets/img/4.png" />
          <img src="./assets/img/5.png" />
          <img src="./assets/img/7.png" />
          <img src="./assets/img/8.png" />
          <img src="./assets/img/6.png" />
          <img src="./assets/img/9.png" />
          <img src="./assets/img/10.png" />
          <img src="./assets/img/11.png" />
          <img src="./assets/img/12.png" />
        </div>
      </div>

      <Migrate />

      <Roadmap />

      <Team />

      <Attributes />

      <div class="page-footer"></div>
    </div>
  </TransitionRoot>
</template>

<script>
import { ref } from "vue";
import { TransitionRoot } from "@headlessui/vue";

import Stats from './components/Stats.vue'
import Attributes from './components/Attributes.vue'
import Roadmap from './components/Roadmap.vue'
import Team from './components/Team.vue'
import Migrate from './components/Migrate.vue'

export default {
  setup() {
    const loading = ref(true);
    setTimeout(function () {
      loading.value = false;
    }, 750);

    return {
      loading,
    };
  },
  components: {
    TransitionRoot,
    Stats,
    Attributes,
    Roadmap,
    Team,
    Migrate
  },
};
</script>
