<template>
  <div>
    <HeroHeader />
    <Perks />
    <SyncVideo />
    <FAQ />
    <DiscordInvitation />
    <HowItWorks />
  </div>
</template>

<script>
import SyncVideo from '~/components/SyncVideo.vue'
import HeroHeader from '~/components/HeroHeader/HeroHeader.vue'
import HowItWorks from '~/components/HowItWorks.vue'
import DiscordInvitation from '~/components/DiscordInvitation.vue'
import FAQ from '~/components/FAQ.vue'
import Perks from '~/components/Perks.vue'

export default {
  components: {
    HeroHeader,
    SyncVideo,
    HowItWorks,
    DiscordInvitation,
    FAQ,
    Perks
  },
  mounted() {
    if (window.location.hash === '#gettingStarted') {
      document.querySelector('#gettingStarted').scrollIntoView()
    }
  },
  head() {
    return {
      title: 'Jelly Party'
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@500&display=swap');
#jellyfish {
  height: 40vh;
  max-width: 40vh;
  position: relative;
}

body {
  font-family: 'Roboto', sans-serif;
}

.inline-svg {
  margin-right: 1em;
  height: 20px;
}

.custom-button {
  position: relative;
  padding: 10px 20px;
  border: none;
  background: none;
  cursor: pointer;
  white-space: nowrap;

  font-size: 30px;
  color: var(--text-color);

  background-color: var(--btn-color);
  box-shadow: var(--shadow-color) 2px 2px 22px;
  border-radius: 4px;
  z-index: 0;
  overflow: hidden;
}

.custom-button:focus {
  outline-color: transparent;
  box-shadow: var(--btn-color) 2px 2px 22px;
}

.right::after,
.custom-button::after {
  content: var(--content);
  display: block;
  position: absolute;
  white-space: nowrap;
  padding: 40px 40px;
  pointer-events: none;
}

.custom-button::after {
  font-weight: 200;
  top: -30px;
  left: -20px;
}

.right,
.left {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
}

.right {
  left: 66%;
}

.left {
  right: 66%;
}

.right::after {
  top: -30px;
  left: calc(-66% - 20px);
  background-color: var(--bg-color);
  color: transparent;
  transition: transform 0.4s ease-out;
  transform: translate(0, -90%) rotate(0deg);
}

.custom-button:hover .right::after {
  transform: translate(0, -47%) rotate(0deg);
}

.custom-button .right:hover::after {
  transform: translate(0, -50%) rotate(-7deg);
}

.custom-button .left:hover ~ .right::after {
  transform: translate(0, -50%) rotate(7deg);
}

/* bubbles */
.custom-button::before {
  content: '';
  pointer-events: none;
  opacity: 0.6;
  background: radial-gradient(
      circle at 20% 35%,
      transparent 0,
      transparent 2px,
      var(--text-color) 3px,
      var(--text-color) 4px,
      transparent 4px
    ),
    radial-gradient(
      circle at 75% 44%,
      transparent 0,
      transparent 2px,
      var(--text-color) 3px,
      var(--text-color) 4px,
      transparent 4px
    ),
    radial-gradient(
      circle at 46% 52%,
      transparent 0,
      transparent 4px,
      var(--text-color) 5px,
      var(--text-color) 6px,
      transparent 6px
    );

  width: 100%;
  height: 300%;
  top: 0;
  left: 0;
  position: absolute;
  animation: bubbles 5s linear infinite both;
}

@keyframes bubbles {
  from {
    transform: translate();
  }

  to {
    transform: translate(0, -66.666%);
  }
}

:root {
  --text-color: hsla(210, 50%, 85%, 1);
  --shadow-color: hsla(210, 40%, 52%, 0.4);
  --btn-color: hsl(210, 80%, 42%);
  --bg-color: #141218;
}

a {
  text-decoration: none !important;
}

.nav-button {
  border-bottom-right-radius: 5px;
  display: inline-block;
  color: white;
}
</style>
