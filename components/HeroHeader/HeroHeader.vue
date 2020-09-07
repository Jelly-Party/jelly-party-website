<template>
  <b-jumbotron
    style="
    position: relative;
      min-height: 90vh;
      background: linear-gradient(to bottom right, #ff9494 0%, #ee64f6 100%);
    "
    class="mb-0"
  >
    <b-container>
      <h1 class="display-3 text-white mb-0">Watch anything. Together.</h1>
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
        <b-col xl="4" class="d-flex align-items-center justify-content-center">
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
    <div class="custom-shape-divider-bottom-1599467513">
      <svg
        data-name="Layer 1"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1200 120"
        preserveAspectRatio="none"
      >
        <path
          d="M0,0V46.29c47.79,22.2,103.59,32.17,158,28,70.36-5.37,136.33-33.31,206.8-37.5C438.64,32.43,512.34,53.67,583,72.05c69.27,18,138.3,24.88,209.4,13.08,36.15-6,69.85-17.84,104.45-29.34C989.49,25,1113-14.29,1200,52.47V0Z"
          opacity=".25"
          class="shape-fill"
        ></path>
        <path
          d="M0,0V15.81C13,36.92,27.64,56.86,47.69,72.05,99.41,111.27,165,111,224.58,91.58c31.15-10.15,60.09-26.07,89.67-39.8,40.92-19,84.73-46,130.83-49.67,36.26-2.85,70.9,9.42,98.6,31.56,31.77,25.39,62.32,62,103.63,73,40.44,10.79,81.35-6.69,119.13-24.28s75.16-39,116.92-43.05c59.73-5.85,113.28,22.88,168.9,38.84,30.2,8.66,59,6.17,87.09-7.5,22.43-10.89,48-26.93,60.65-49.24V0Z"
          opacity=".5"
          class="shape-fill"
        ></path>
        <path
          d="M0,0V5.63C149.93,59,314.09,71.32,475.83,42.57c43-7.64,84.23-20.12,127.61-26.46,59-8.63,112.48,12.24,165.56,35.4C827.93,77.22,886,95.24,951.2,90c86.53-7,172.46-45.71,248.8-84.81V0Z"
          class="shape-fill"
        ></path>
      </svg>
    </div>
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

<style>
.custom-shape-divider-bottom-1599467513 {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
  transform: rotate(180deg);
}

.custom-shape-divider-bottom-1599467513 svg {
  position: relative;
  display: block;
  width: calc(100% + 1.3px);
  height: 126px;
  transform: rotateY(180deg);
}

.custom-shape-divider-bottom-1599467513 .shape-fill {
  fill: #ffffff;
}
</style>
