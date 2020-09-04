<template>
  <b-container
    fluid
    class="py-5 mb-5"
    style="background: linear-gradient(to bottom right,#9164ff 0,#8bfff4)"
  >
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
</style>
