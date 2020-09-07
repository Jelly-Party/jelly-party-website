<template>
  <b-container id="feedbackContainer" fluid>
    <div class="custom-shape-divider-top-1599468478">
      <svg
        data-name="Layer 1"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1200 120"
        preserveAspectRatio="none"
      >
        <path
          d="M598.97 114.72L0 0 0 120 1200 120 1200 0 598.97 114.72z"
          class="shape-fill"
        ></path>
      </svg>
    </div>
    <b-container class="d-flex flex-column align-items-center pb-5">
      <h1 class="text-center text-white display-4">
        Got Feedback? We're listening.
      </h1>
      <p class="text-center text-white lead">
        Simply join our discord channel and let us know. Or fill out our
        <a href="feedback">feedback form</a>. <br />
      </p>
      <iframe
        src="https://discordapp.com/widget?id=702231955391119471&theme=dark"
        width="350"
        height="500"
        allowtransparency="true"
        frameborder="0"
      ></iframe>

      <p class="text-white">
        <span style="font-size: 0.7em"
          >Or shoot us an email at
          <a href="mailto:hi@jelly-party.com">hi@jelly-party.com</a>
        </span>
      </p>
    </b-container>
  </b-container>
</template>

<script>
export default {}
</script>

<style>
#feedbackContainer {
  position: relative;
  padding-top: 5em;
  background: linear-gradient(
    to right bottom,
    rgb(255, 148, 148) 0%,
    rgb(238, 100, 246) 100%
  );
}
.custom-shape-divider-top-1599468478 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
  transform: rotate(180deg);
}

.custom-shape-divider-top-1599468478 svg {
  position: relative;
  display: block;
  width: calc(100% + 1.3px);
  height: 55px;
}

.custom-shape-divider-top-1599468478 .shape-fill {
  fill: #ffffff;
}
</style>
