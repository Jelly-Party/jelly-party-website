<template>
  <b-container fluid class="video-container">
    <b-row>
      <b-col
        xl="4"
        class="mt-5 d-flex align-items-center justify-content-center"
      >
        <h1 class="mt-2 mb-2 text-white text-center" style="max-width: 10em">
          Jelly-Party runs in your Chrome/Firefox/Edge browser on Windows,
          macOs, ChromeOS &amp; Linux.
        </h1>
      </b-col>
      <b-col
        xl="8"
        class="mt-5 d-flex align-items-center justify-content-center mb-5 mt-5"
      >
        <video
          id="alpha-video"
          style="max-width: 1080px"
          muted
          loop
          src="~/assets/promo.webm"
          width="100%"
        ></video>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
const supportsWebMAlpha = function(callback) {
  const vid = document.createElement('video')
  vid.autoplay = false
  vid.loop = false
  vid.style.display = 'none'
  vid.addEventListener(
    'loadeddata',
    function() {
      document.body.removeChild(vid)
      // Create a canvas element, this is what user sees.
      const canvas = document.createElement('canvas')

      // If we don't support the canvas, we definitely don't support webm alpha video.
      if (!(canvas.getContext && canvas.getContext('2d'))) {
        // eslint-disable-next-line standard/no-callback-literal
        callback(false)
        return
      }

      // Get the drawing context for canvas.
      const ctx = canvas.getContext('2d')

      // Draw the current frame of video onto canvas.
      ctx.drawImage(vid, 0, 0)
      if (ctx.getImageData(0, 0, 1, 1).data[3] === 0) {
        // eslint-disable-next-line standard/no-callback-literal
        callback(true)
      } else {
        // eslint-disable-next-line standard/no-callback-literal
        callback(false)
      }
    },
    false
  )
  vid.addEventListener('error', function() {
    document.body.removeChild(vid)
    // eslint-disable-next-line standard/no-callback-literal
    callback(false)
  })

  vid.addEventListener('stalled', function() {
    document.body.removeChild(vid)
    // eslint-disable-next-line standard/no-callback-literal
    callback(false)
  })

  // Just in case
  vid.addEventListener('abort', function() {
    document.body.removeChild(vid)
    // eslint-disable-next-line standard/no-callback-literal
    callback(false)
  })

  const source = document.createElement('source')
  source.src =
    'data:video/webm;base64,GkXfowEAAAAAAAAfQoaBAUL3gQFC8oEEQvOBCEKChHdlYm1Ch4ECQoWBAhhTgGcBAAAAAAACBRFNm3RALE27i1OrhBVJqWZTrIHlTbuMU6uEFlSua1OsggEjTbuMU6uEHFO7a1OsggHo7AEAAAAAAACqAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAVSalmAQAAAAAAADIq17GDD0JATYCNTGF2ZjU3LjU3LjEwMFdBjUxhdmY1Ny41Ny4xMDBEiYhARAAAAAAAABZUrmsBAAAAAAAARq4BAAAAAAAAPdeBAXPFgQGcgQAitZyDdW5khoVWX1ZQOYOBASPjg4QCYloA4AEAAAAAAAARsIFAuoFAmoECU8CBAVSygQQfQ7Z1AQAAAAAAAGfngQCgAQAAAAAAAFuhooEAAACCSYNCAAPwA/YAOCQcGFQAADBgAABnP///NXgndmB1oQEAAAAAAAAtpgEAAAAAAAAk7oEBpZ+CSYNCAAPwA/YAOCQcGFQAADBgAABnP///Vttk7swAHFO7awEAAAAAAAARu4+zgQC3iveBAfGCAXXwgQM='
  source.addEventListener('error', function() {
    document.body.removeChild(vid)
    // eslint-disable-next-line standard/no-callback-literal
    callback(false)
  })
  vid.appendChild(source)

  // This is required for IE
  document.body.appendChild(vid)
}

export default {
  mounted() {
    const options = {
      root: null, // default to viewport
      rootMargin: '0px',
      threshold: 0.8
    }
    const target = document.querySelector('#alpha-video')
    const callback = (entries, observer) => {
      entries.forEach((entry) => {
        if (entry.intersectionRatio > 0) {
          if (target.paused) {
            target.play()
            observer.unobserve(entry.target)
            // console.log('Autoplaying with IntersectionObserver!')
          }
        }
      })
    }
    const observer = new IntersectionObserver(callback, options)
    observer.observe(target)
    supportsWebMAlpha(function(result) {
      if (result) {
        // alert('Supports WebM Alpha')
      } else {
        document.querySelector('.video-container').style.display = 'none'
        // alert("Doesn't support WebM Alpha")
      }
    })
  }
}
</script>

<style scoped>
.video-container {
  background: linear-gradient(to bottom right, #9164ff 0%, #8bfff4 100%);
}
</style>
