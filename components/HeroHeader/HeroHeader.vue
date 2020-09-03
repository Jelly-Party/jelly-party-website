<template>
  <b-jumbotron
    style="
      min-height: 70vh;
      background: linear-gradient(to bottom right, #ff9494 0%, #ee64f6 100%);
    "
    class="mb-0"
  >
    <b-container>
      <h1 class="display-3 text-white mb-0 mt-5">Watch anything. Together.</h1>
      <p class="text-white">
        * Runs on Chrome/Firefox/Edge. Paid services require every participant's
        subscription.
      </p>
      <SupportedServices />
    </b-container>
    <b-container fluid>
      <b-row>
        <b-col xl="4" class="mb-5 d-none d-sm-block">
          <div class="d-flex justify-content-center w-100">
            <svg
              id="jellyfish"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              viewBox="0 0 512 512"
              preserveAspectRatio="xMidYMid meet"
              width="100%"
            >
              <defs>
                <style>
                  .cls-1 {
                    fill: #fff;
                  }

                  .cls-2 {
                    fill: url(#linear-gradient);
                  }
                </style>
                <linearGradient
                  id="linear-gradient"
                  x1="32"
                  y1="256"
                  x2="480"
                  y2="256"
                  gradientUnits="userSpaceOnUse"
                >
                  <stop offset="0" stop-color="#9164ff" />
                  <stop offset="0.725" stop-color="#8bfff4" />
                  <stop offset="1" stop-color="#8bfff4" />
                </linearGradient>
              </defs>
              <title>&deg;&deg;&deg;&deg;</title>
              <g id="Layer_3" data-name="Layer 3">
                <path
                  class="cls-1"
                  d="M414.3921,97.6079A224,224,0,0,0,32,256v48a16,16,0,0,0,16,16H464a16,16,0,0,0,16-16V256A222.5338,222.5338,0,0,0,414.3921,97.6079Z"
                />
                <path
                  class="cls-2"
                  d="M414.3916,97.6079A224,224,0,0,0,32,256v48a16,16,0,0,0,16,16H96v48a16.0183,16.0183,0,0,1-16,16,16,16,0,0,0,0,32,48.054,48.054,0,0,0,48-48V320h64V432a16.0183,16.0183,0,0,1-16,16,16,16,0,0,0,0,32,48.054,48.054,0,0,0,48-48V320h64V432a48.054,48.054,0,0,0,48,48,16,16,0,0,0,0-32,16.0183,16.0183,0,0,1-16-16V320h64v48a48.054,48.054,0,0,0,48,48,16,16,0,0,0,0-32,16.0183,16.0183,0,0,1-16-16V320h48a16,16,0,0,0,16-16V256A222.5322,222.5322,0,0,0,414.3916,97.6079Zm-228.9,59.273a127.8013,127.8013,0,0,0-28.1279,28.3862,16,16,0,0,1-26.086-18.5342,157.9553,157.9553,0,0,1,35.2315-35.6138,16,16,0,1,1,18.9824,25.7618Z"
                />
              </g>
            </svg>
          </div>
        </b-col>
        <b-col
          xl="4"
          class="d-flex align-items-center justify-content-center mb-5"
        >
          <p class="lead text-white text-center" style="max-width: 20em">
            Jelly-Party synchronizes videos you play in your browser, so that
            you and your friends can enjoy your favorite content —
            <span style="font-weight: 600"> together.</span>
            <br />
            <br />
            <small>
              Please consider leaving us <a href="feedback">feedback</a>.
            </small>
          </p>
        </b-col>
        <b-col
          xl="4"
          class="d-flex align-items-center justify-content-center mb-5"
        >
          <a :href="getDownloadLink"
            ><button
              id="ctaButton"
              class="custom-button"
              style="--content: 'Get the extension now!'"
            >
              <div class="left"></div>
              Get the extension now!
              <div class="right"></div></button
          ></a>
        </b-col>
      </b-row>
    </b-container>
  </b-jumbotron>
</template>

<script>
import gsap from 'gsap'
import SupportedServices from './SupportedServices.vue'

export default {
  components: {
    SupportedServices
  },
  computed: {
    getDownloadLink() {
      if (window.navigator.userAgent.includes('Firefox')) {
        return 'https://addons.mozilla.org/en-US/firefox/addon/jelly-party/'
      } else {
        return 'https://chrome.google.com/webstore/detail/jelly-party/aiecbkandfgpphpdilbaaagnampmdgpd'
      }
    }
  },
  mounted() {
    function flickerAnimate(object) {
      const tl = gsap.timeline()
      const randomDuration = Math.random() * 0.5 + 1.5
      const randomRotation =
        (Math.random() > 0.5 ? '-' : '') + (Math.random() * 10 + 2) + 'deg'
      const randomX =
        (Math.random() > 0.5 ? -1 : 1) * Math.random() * 20 * excitement
      const randomY =
        (Math.random() > 0.5 ? -1 : 1) * Math.random() * 20 * excitement + 20
      tl.to(object, {
        duration: randomDuration / excitement,
        x: randomX,
        y: randomY,
        rotate: randomRotation,
        onComplete: flickerAnimate,
        onCompleteParams: [object]
      })
    }
    let excitement = 1
    const ctaButton = document.getElementById('ctaButton')
    const jellyfish = document.getElementById('jellyfish')
    ctaButton.addEventListener('mouseenter', () => {
      gsap.to(jellyfish, { duration: 0.2, rotation: '360deg' })
      excitement = 5
    })
    ctaButton.addEventListener('mouseleave', () => {
      excitement = 1
    })
    flickerAnimate(jellyfish)
  }
}
</script>

<style></style>
