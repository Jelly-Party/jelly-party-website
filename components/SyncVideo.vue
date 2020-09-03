<template>
  <b-container>
    <h1 class="text-center mt-5 display-4 mb-0">Sync your watch parties!</h1>
    <p class="lead text-center mb-5">
      Host next level watch parties with your friends. No registration required!
      Free &amp; <a href="https://github.com/Jelly-Party">open source</a>!
    </p>
    <div id="videoWrapper">
      <video
        id="syncVideo1"
        class="syncVideo"
        muted
        loop
        src="~/assets/SyncVideo.mp4"
        width="720px"
      ></video>
      <video
        id="syncVideo2"
        class="syncVideo"
        muted
        loop
        src="~/assets/SyncVideo.mp4"
        width="720px"
      ></video>
    </div>
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
  top: -150px;
  right: -250px;
}

#videoWrapper {
  width: min-content;
  margin: 0 auto;
  position: relative;
  left: -125px;
}
</style>
