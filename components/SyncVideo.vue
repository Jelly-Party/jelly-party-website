<template>
  <b-container
    fluid
    class="pb-5 mb-5"
    style="background: linear-gradient(to bottom right,#9164ff 0,#8bfff4); position: relative; padding-top: 10em"
  >
    <div class="custom-shape-divider-top-1599468434">
      <svg
        data-name="Layer 1"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1200 120"
        preserveAspectRatio="none"
      >
        <path
          d="M985.66,92.83C906.67,72,823.78,31,743.84,14.19c-82.26-17.34-168.06-16.33-250.45.39-57.84,11.73-114,31.07-172,41.86A600.21,600.21,0,0,1,0,27.35V120H1200V95.8C1132.19,118.92,1055.71,111.31,985.66,92.83Z"
          class="shape-fill"
        ></path>
      </svg>
    </div>
    <div class="custom-shape-divider-bottom-1599468241">
      <svg
        data-name="Layer 1"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1200 120"
        preserveAspectRatio="none"
      >
        <path
          d="M985.66,92.83C906.67,72,823.78,31,743.84,14.19c-82.26-17.34-168.06-16.33-250.45.39-57.84,11.73-114,31.07-172,41.86A600.21,600.21,0,0,1,0,27.35V120H1200V95.8C1132.19,118.92,1055.71,111.31,985.66,92.83Z"
          class="shape-fill"
        ></path>
      </svg>
    </div>
    <b-row>
      <b-col
        lg
        class="d-flex flex-column align-items-center justify-content-center"
        style="flex-grow: 1"
      >
        <h1 class="text-center display-4 mb-0 text-white">
          Sync your watch parties!
        </h1>
        <p class="lead text-center mb-5 text-white">
          Host next level watch parties with your friends. No registration
          required! Free &amp;
          <a href="https://github.com/Jelly-Party">open source</a>!
        </p>
      </b-col>
      <b-col
        lg
        style="flex-grow: 2"
        class="d-flex flex-column align-items-center"
      >
        <video
          id="syncVideo1"
          class="syncVideo"
          muted
          loop
          src="~/assets/SyncVideo.mp4"
          width="70%"
          style="margin-right: 20%"
        ></video>
        <video
          id="syncVideo2"
          class="syncVideo"
          muted
          loop
          src="~/assets/SyncVideo.mp4"
          width="50%"
        ></video>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  mounted() {
    const syncVideo1 = document.querySelector('#syncVideo1')
    const syncVideo2 = document.querySelector('#syncVideo2')
    const resetVideos = () => {
      syncVideo1.load()
      syncVideo1.play()
      window.setTimeout(() => {
        syncVideo2.load()
        syncVideo2.play()
      }, 200)
    }
    syncVideo1.addEventListener('ended', resetVideos)
    resetVideos()
  }
}
</script>

<style>
#syncVideo2 {
  position: relative;
  top: -20%;
  margin-bottom: -10%;
  right: -20%;
}
.custom-shape-divider-top-1599468434 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
  transform: rotate(180deg);
}

.custom-shape-divider-top-1599468434 svg {
  position: relative;
  display: block;
  width: calc(100% + 1.3px);
  height: 55px;
}

.custom-shape-divider-top-1599468434 .shape-fill {
  fill: #ffffff;
}
.custom-shape-divider-bottom-1599468241 {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
}

.custom-shape-divider-bottom-1599468241 svg {
  position: relative;
  display: block;
  width: calc(169% + 1.3px);
  height: 42px;
  transform: rotateY(180deg);
}

.custom-shape-divider-bottom-1599468241 .shape-fill {
  fill: #ffffff;
}
</style>
