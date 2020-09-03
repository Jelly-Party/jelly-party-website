<template>
  <b-container fluid id="feedbackContainer">
    <b-container class="d-flex flex-column align-items-center pb-5 pt-5">
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
  background: linear-gradient(
    to right bottom,
    rgb(255, 148, 148) 0%,
    rgb(238, 100, 246) 100%
  );
}
</style>
